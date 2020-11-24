.. _rfc-8:

RFC 8: GM 3 - Vector Editing
=============================

+---------------------+---------------+
| **Status:**         | Proposed      |
+---------------------+---------------+
| **Last Updated:**   | 2020-11-24    |
+---------------------+---------------+

+----------------+---------------------------+
| **Authors:**   | **Contact:**              |
+================+===========================+
| Brent Fraser   | GitHub: @brentfraser      |
+----------------+---------------------------+
| Dan Little     | GitHub: @theduckylittle   |
+----------------+---------------------------+

Overview and Scope
------------------

For some web mapping sites, it is necessary to allow browser-based
editing of vector map features. These GeoMoose v3 enhancements will add
the ability to connect to a WFS-T server to save the edits to the
geometry and attributes of point line and polygon vector features.

Requirements
------------

Must-Have Requirements
~~~~~~~~~~~~~~~~~~~~~~~

1. Enable create, edit, delete and save of vector map features on a web
   server using GeoMoose 3 as the front-end, current GeoServer 2.x as
   the back-end and the existing WFS-T 1.1.0 protocol.

2. The primary need is to edit polygons, with points and line features
   being secondary.

3. The user must be able to edit both geometry and attribute values.

4. Performance is very important. Loading all (or even a bounding-box
   subset) of the features for a vector data source can take multiple
   seconds and should be avoided. This may imply a dual-layer approach
   (like the GeoMoose 2.8 implementation of editing): one read-only
   layer for display/selection, another layer for editing of a single
   feature. A precedent for the dual-layer approach exists in GeoMoose
   3.x for query operations using the ``query-as`` attribute on a WMS
   layer.

5. The solution must allow the admin to specify the geometryName
   expected by the server to override any default assumed by GeoMoose or
   OpenLayers.

6. The solution must handle the WFS server feature coordinates to be
   different from the GeoMoose map srs. For example, a typical
   configuration would be for the WFS server to store and publish
   feature coordinates in EPSG:4286 while the map/display SRS might be
   EPSG:3857. This may imply having GeoMoose convert the feature's
   geometry using existing OpenLayers methods.

7. Feature Locking is not required (Feature Locking is allowed with
   WFS-T 1.1.0 and 2.0.0).

8. For attribute editing, the usual data types will be supported (string,
   integer, real), as well as an "enum"-type to provide a select
   dropdown for the user to select specific values. Bonus: The enum list
   can come from a URL.

Other Considerations
^^^^^^^^^^^^^^^^^^^^

An automatic refresh of the read-only (e.g WMS) layer will be necessary
after editing the referenced WFS-T features.

Proxying the WFS-T server will be necessary if the GeoMoose JavaScript
is delivered from an address different from the WFS-T server. This can
be configured on the web server.

-  Properties will be edited using the current property editing dialog.
-  An enum-type should be defined with a select-drop down.

Proposed User Workflows
^^^^^^^^^^^^^^^^^^^^^^^

The site administrator would:

-  install and configure a WFS-T server.
-  configure GeoMoose files (e.g. mapbook.xml) to enable editing of
   features for specific layers.

The end-user would, using web browser:

-  select the layer for editing from Catalog's layer list
-  select the edit tool (create, edit geometry/attributes, delete)
-  edit the feature
-  save the edit.

Additional GeoMoose Community Perspectives
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Other WFS-T servers should be tested if possible.
`TinyOWS <https://github.com/mapserver/tinyows/>`__ supports WFS-T 1.1.0

--------------

Proposed Solution
-----------------

The enhancements made to address this RFC will support editing using
WFS-T 1.1.0 only.

User Interface
~~~~~~~~~~~~~~

Catalog controls

Attribute Editing
^^^^^^^^^^^^^^^^^

Attributes can be edited using the same dialog roughed-in for the
Sketches attributes.

Geometry editing
^^^^^^^^^^^^^^^^

Geometry editing should work similar to the current workflow for using
the Sketch layer. It will need some adaptations in order to work with
hybrid layers.

-  User selects "Edit Geometry" from the catalog's layer (layer must be
   on).
-  User clicks on the map to select a feature.
-  GM fetches feature from the WFS-T source.
-  GM renders the feature in a temporary layer for editing.
-  User edits geometry.
-  GM offers to cancel or save the feature. This will replace the
   current 'End Drawing' map control.
-  User clicks save:
-  GM posts the feature to the WFS-T source.
-  GM displays success/failure message (ToDo:where?)
-  GM updates layer (ToDo: refreshes WMS layer, or replaces feature in
   WFS layer)
-  User clicks cancel: GM will dispose of the temporary feature being
   edited.

Configuring GeoMoose
^^^^^^^^^^^^^^^^^^^^

mapbook.xml:

::

        <map-source name="census_cities-wms" type="wms">
            <url>/geoserver/GeoMOOSE_Testing/wms?</url>
            <layer name="GeoMOOSE_Testing:census_cities" query-as="census_cities-wfs/census_cities" status="on">
            </layer>
            <param name="INFO_FORMAT" value ="text/html" />
            <param name="FORMAT" value="image/png"/>
            <param name="TRANSPARENT" value="TRUE"/>
        </map-source>
        
        <map-source name="census_cities-wfs" type="wfs" status="on">
            <url>/geoserver/GeoMOOSE_Testing/ows</url>
            <param  name="typename" value="GeoMOOSE_Testing:census_cities"/>
            <config name="geometry-name" value="wkb_geometry"/>
            <layer  name="census_cities" status="off" >
                <style><![CDATA[
                {
                    "line-color": "#d95f0e",
                    "line-width": 4,
                    "line-opacity": 0.80,
                    "fill-color": "#fec44f",
                    "fill-opacity": 0.60,
                    "text-size": 16.0,
                    "text-field": "{name}",
                    "text-color": "#A16214"            }
                ]]></style>
                <template name="identify" auto="true" />
                <template name="select"   auto="true" />
            </layer>
            <properties>
                <property name="name" label="Name" type="string" default="" />            
                <property name="name" label="Name (full)" type="string" default="" />
                <property name="aland" label="Area (land)" type="number" default="" />            
                <property name="awater" label="Area (water)" type="number" default="" />            
            </properties>        
        </map-source>
    ...
        <catalog>
        
          <group title="Vector Editing" expand="true">
            <layer title="Places (WMS)" src="census_cities-wms/GeoMOOSE_Testing:census_cities"
               draw-polygon="true"
               draw-modify="true" 
               draw-remove="true" 
               draw-edit="true"             
            />
            <layer title="Places (WFS)" src="census_cities-wfs/census_cities"
               draw-polygon="true"
               draw-modify="true" 
               draw-remove="true" 
               draw-edit="true"             
            />
          </group>

        </catalog>

``app.js:`` No changes to the ``app.js`` file are be necessary. Editing
is built into the main library.

Performance Implications
~~~~~~~~~~~~~~~~~~~~~~~~

As this uses current functionality (see the sketch layer) and WMS
rendering there should be minimal impacts on performance.

Compatibility and Dependencies
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  OpenLayers 6

GM Enhancements **WILL** work for: - WFS 1.1.0 (OL6 default), uses GML
3.1.1

GM Enhancements **MAY** work for: - WFS 1.0.0 (supported by OL6), uses
GML 2

GM Enhancements **WILL NOT** work for: - WFS 2.0 (not currently
supported by OL6), uses GML 3.2

Security Implications
~~~~~~~~~~~~~~~~~~~~~

Authentication and Permissions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

No specific code changes will be included to address user authentication
and permissions. For admins wanting to restrict access to users
submitting changes to the GIS database, they can use network security or
scripting-based client-server session handling.

Injection implications No specific code changes will be included to
address SQL injection.

For GeoServer security implementation, see: -
https://docs.geoserver.org/master/en/user/production/config.html#set-security
- https://docs.geoserver.org/master/en/user/data/database/sqlview.html

Documentation Needs
~~~~~~~~~~~~~~~~~~~

GeoMoose Documentation will include a "How-To" on configuring GeoServer,
loading sample data and configuring the mapbook.xml

Example/Demo
~~~~~~~~~~~~

Add point, line, and polygon mapsources to desktop example these will be
commented out as they require a WFS-T server to function.

Filed Issues and Other References
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Issues:
^^^^^^^

https://github.com/geomoose/gm3/issues/47

Other References
^^^^^^^^^^^^^^^^

-  `OpenLayers API -
   WFS <https://openlayers.org/en/latest/apidoc/module-ol_format_WFS-WFS.html#writeTransaction>`__
-  `GeoServer
   WFS <https://docs.geoserver.org/latest/en/user/services/wfs/reference.html>`__
-  `TinyOWS <https://github.com/mapserver/tinyows/>`__
-  `Mapserver's future OGC
   API <https://github.com/mapserver/mapserver/wiki/OGC-API-implementation-RFC>`__
-  `OL3
   example <https://github.com/Luka-G/OpenLayers3_WFS-T/blob/master/javascript/wfst-javascript.js>`__

Testing
~~~~~~~

Interactive Testing
^^^^^^^^^^^^^^^^^^^

It will be possible to interactively test WFS-T by following the
GeoMoose How-To documentation. This will include installing PostGIS,
GeoServer (or TinyOWS), loading the sample data, and uncommenting the
sections of the the desktop demo.

When testing using the npm development environment, edit the
webpack.config.js to add a proxy rule pointing to the GeoServer
instance:

::

                {
                    context: ['/geoserver'],
                    target: 'http://localhost:8080/',
                    secure: false
                }, 

Automated Testing
^^^^^^^^^^^^^^^^^

End to end testing will not be added but unit testing assuring messages
are properly constructed will be added.

Voting History
--------------
