Older News
=============

5/19/2023 - GeoMoose 3.11.0 Released
------------------------------------
Lots of fixes and some new stuff. See :ref:`3.11.0_Release` for details.

7/29/2022 - GeoMoose 3.10.1 Released
-----------------------------------

Small bugfix release: restore highligh defaults, fix geocoder.  See :ref:`3.10.1_Release` for details.

6/28/2022 - GeoMoose 3.10.0 Released
-----------------------------------

Security updates of dependencies, new feature to disable highlight for a layer and service.  See :ref:`3.10.0_Release` for details.

3/24/2022 - GeoMoose 3.9.0 Released
-----------------------------------

Lots of bugfixes, some new features.  See :ref:`3.9.0_Release` for details.

8/30/2021 - GeoMoose 3.8.0 Released
-----------------------------------

WFS-T Editing is here! Also included are many bugfixes, new translations,
and major updates of the documentation. 

2/8/2021 - GeoMoose 3.7.0 Released
----------------------------------

While the team is busy at work with new editing features, we
have also snuck in a solid maintenance release!

* Updated underlying dependency libraries.
* Added support for rendering the USNG grid on the map.
* Lat/Lon coordinate precision will now adjust based on the zoom level.
* The catalog can now be hidden.
* Added new Bookmark Modal dialog.
* Updated and reorganized docs.
* Legends can now be included in print outputs!

9/14/2020 - Happenings in the 'Moose World
------------------------------------------

Hey folks! It's been a few months since a release but we 
are actively working on a 3.7! We are also doing some planning
on longer term projects such as updating the styling APIs
and bringing back editing.

We are also seeking anyone interested in participating more actively
in the project by becoming involved in the PSC. Feel free to email the
mailing list, or the PSC chair directly (theduckylittle / gmail.com).

6/17/2020 - GeoMoose 3.6.2 - Bug fix release
--------------------------------------------

Squashed a few more bugs that made their way into 3.6.

:ref:`3.6.2_Release` details what was fixed.


5/28/2020 - GeoMoose 3.6.1 - The beauty of open source
------------------------------------------------------

A few missed bugs were found in the initial release!
But thanks to some dedicated effort, the bugs were fixed
and a new release was put together. 

:ref:`3.6.1_Release` details what was fixed.

5/27/2020 - GeoMoose 3.6.0 Release
----------------------------------

This is a *giant one*! A lot of work has gone into new features
and bringing up parity with the last 2.X versions of GeoMoose.

The release notes have a complete list but these are some of the highlights:

* i18n support! Yes! Translation is available for nearly every element in the UI.
  The translation tools are even applied to labels coming in from the mapbook, allowing
  the mapbook to more language agnostic as well as the built-in tools and strings!
* More search options! The demo has been configured to allow for a number of improved
  searching options. Including the ability to search multiple fields with multiple search terms!
* Drawing and Markup layer now supports labels!
* The Select service now supports keepAlive. This allows keeping the last draw tool "alive" after results have returned to allow repeated selections.
* Results from the grid can now be buffered! There is a new tool to allow buffering a specific result from the table. This is fuller realized version of the GM 2.X "buffer follow up" service.
* A number of state-bugs have been fixed and internal state has been simplified
  to prevent them in the future.
* React, OpenLayers, and the associated dependencies have all been upgraded to their latest versions.


See :ref:`3.6.0_Release` for more!


4/15/2020 - More new features coming soon!
------------------------------------------

A big thanks to some generous sponsorship have helped move a
few GeoMoose features forward!

 * New search examples that demonstrate how to do a single-search field to search multiple fields.
 * Upgraded OpenLayers to OpenLayers 6.1! This has a ton of performance improvements and enables better vector styling.
 * Thanks to the upgrade in OpenLayers, the Drawing and Markup layer will get labels!

3/28/2020 - GeoMoose 3.5.1 Release
----------------------------------

A minor bugfix release.

See :ref:`3.5.1_Release` for more!

2/12/2020 - GeoMoose 3.5.0 Release
----------------------------------

The GeoMoose team has been busy the past few months.  Lot's of hard work has produced many bug fixes and new features. Be sure to check out the new version.

See :ref:`3.5.0_Release` for more!

8/30/2019 - GeoMoose 3.4.0 Release
----------------------------------

Fixed select with autogo=true.  Added support for attribution on the map.
See :ref:`3.4.0_Release` for more!

5/17/2019 - GeoMoose 3.3.1 Release
----------------------------------

Fixed a few major bugs from the OpenLayers 5 upgrade and
corrected a few long standing issues. See :ref:`3.3.1_Release` for more!

2/6/2019 - GeoMoose 3.3.0 Release
----------------------------------------

Lots of bug fixes and a few new features.  See :ref:`3.3.0_Release` for details.


11/6/2018 - GeoMoose 2.x Retirement - April 2019
------------------------------------------------

Summary:

Due to GeoMoose 2.x requiring now very old versions of it dependencies it is becoming increasingly difficult to support.  As such, the GeoMoose team is announcing retirement for the GeoMoose 2.x series as April 2019.

This doesn't mean your older GeoMoose installations will suddenly stop working.  However, the GeoMoose 2.9 demo (on https://demo.geomoose.org/2.9) will be shutdown and the development team won't have ready access to develop and test changes to the 2.x series. As such, the GeoMoose team recommends upgrading to GeoMoose 3.x.


Details:

GeoMoose 2.x requires old versions of Dojo (1.6) and OpenLayers (2.13). Neither of these libraries are currently under development or supported upstream. Updating to current versions of these libraries requires major reworking of the GeoMoose 2.x code.  (In fact, this is what prompted the development of the GeoMoose 3.x series).

The bigger problem is that PHP services shipped with GeoMoose 2.x require PHP 5 and PHP MapScript.  These don't exist in recent Linux distributions (e.g. Debian Stretch/Ubuntu 16.04 and newer).  The April 2019 date is set to coincide with Ubuntu 14.04 EOL.


8/13/2018 - Performance improvements coming
-------------------------------------------

Finding GeoMoose 3 a little slow? Tests between GeoMoose 2.X and 3
initially showed quite a few performance benefits. We have still
found this to be true but there's always room for improvement! A few 
major components were doing extra memoization and  taking up way
too much memory.

The branch with the performance improvements is still a work in progress
but for this interested the pull request can be found `here <https://github.com/geomoose/gm3/pull/314>`_!

6/25/2018 - GeoMoose 3.2.1 Release
----------------------------------

Add a polyfill to fix an IE11 regression in 3.2.0.

4/12/2018 - GeoMoose 3.2.0 Release
----------------------------------

After fighting quite a few dependency demons in NPM, we've taken
the time to update the build system! All of our dependencies are
now on the the latest versions.  We've also started to add the
npm "lock" file to the repo to prevent inconsistencies with build
and testing.

:ref:`3.2.0_Release` has more details on all the fixed bugs!

11/28/2017 - GeoMoose 3.1.0 Release
-----------------------------------

Many bug fixes! Great set of new features!

See :ref:`3.1.0_Release` for more details!

9/24/2017 - GeoMoose 3.0.1 Release
----------------------------------

Today's GeoMoose 3.0.1 release contains bug fixes and lots of documentation updates.

See :ref:`3.0.1_Release` for details.

9/11/2017 - Still at it! 3.0.1 on the Horizon
---------------------------------------------

After the great feedback from FOSS4G, and some tickets from early adopters, we've been
studiously working towards the 3.0.1 release.  There will be a great collection of small
changes. Stay tuned for a release! 


8/15/2017 - FOSS4G Workshop Day
-------------------------------

@theduckylittle will be teaching a GeoMoose 3.0.0 workshop at FOSS4G in Boston today!

For those who can't make it, we have made the workshop contents available online. 

Find it in the `GitHub pages <https://docs.geomoose.org/3.x/workshop/index.html>`_. Fun fact, this RST presentation can be turned into PDF slides using pandoc and beamer!

Look for the GeoMoose 3.0.0 presentation tomorrow!

8/10/2017 - 3.0.0 is OFFICIAL!
------------------------------

With a full year of hard work the GeoMoose team is proud to announce the official 3.0.0 release!

This is the first major rewrite of GeoMoose in nearly 10 years. This newest version offers a great
upgrade over the the 2.X line in GeoMoose:

1. Modern JavaScript frameworks.
   GM3 is based on React, OpenLayers 4, JSTS, Babel, and Webpack. This makes GeoMoose
   development and deployment platform independent and easy to extends.

   Not a fan of React and ES6? No fear! GeoMoose's examples are written in traditional JavaScript.

2. We're exercising even more standards.
   GM3 does not use PHP but still can perform identify, select, and buffer operations!
   It does this by using JSTS to do client-side geometry manipulation and the querying capabilities
   of WFS and FeatureServices.

   That also means no more MapServer templates! Templates can now be defined right in the mapbook
   using the Mark.up template engine.

3. There are so many other great features! `Try the Demo <https://demo.geomoose.org>`_ and read the `Quickstarts! <https://docs.geomoose.org/3.x/quickstarts/index.html>`_. The full 3.0.0 documentation can be `found here! <https://docs.geomoose.org/3.x/index.html>`_

Finally, a huge **thank you** to the MN.IT with the Minnesota DOT. They provided a lot of technical assistance, review, and funding for this release! 


7/11/2017 - 3.0.0 is Almost Here!
---------------------------------

After a great showing at ITAG, 3.0.0 is getting even closer to release! There's been a few late-changing bugs that will need to be fixed but we expect to have 3.0.0 ready for everyone by the end of the month!

The biggest gulf right now is the documentation. Much of the older documentation and how-tos will still need "ported forward" to make a real release possible.  The code is *really good* but we are missing that solid documentation component to go with it.

If you get any time please check out the demo and file any issues you may find. We want to get the best out of this first release and it's really starting to gel! We also accept documentation help! If you find a how-to you'd like to rewrite or have solved a problem with 3.0.0 already send it our way. We'd love to put it in!

6/20/2017 - Starting to wrap on 3.0
-----------------------------------

We are getting closer and closer to an official 3.0 release! We've really tackled the last of the major features and can proudly announce that all of the following features work in the latest version of 3.0:

1. Buffering. We're using the ES6-capable version of JSTS to do client-side buffering.  It's been a really great addition and you can see it at work in the new demo.
2. OpenLayers 4. OpenLayers now publishes an `ol` package which is ES6-compatible.  We have adopted it and so now there is no longer a need to separately include OpenLayers in a gm3 application.
3. The metadata tool is back. In all of our development we missed out on the simple metadata tool from the catalog. It's back in the demo.
4. Toolbar drawers. In GM 2.X these were provided by using a very widget heavy set of solutions.  They usually had browser compatibility issues and some struggled to function on touch screens.  The new solution is almost purely CSS based and has been test on modern version of IE, Chrome, Firefox, and on mobile browsers.
5. ArcGIS FeatureServer layers. FeatureServer layers can now be treated the same way as WFS layers. They can be queries and rendered in the browser.  The *AGS Dakota County Rail* layer in the demo has been added as an example to prove how it works and it can be used in the same ways and with services just like any other vector layer.

Thursday, @theduckylittle will be presenting at Iowa's ITAG conference and covering all the new features and doing a live demo.

Please take some time to exercise the demo and file bug reports! The GeoMoose 3 issue list can be found `here on GitHub <https://github.com/geomoose/gm3/issues>`_.

5/2/2017 - Making a (PDF) Mark with GeoMoose 3.0
------------------------------------------------

GeoMoose 3.0 is still moving along! We have put some serious work into preparing packaging and adding a new print tool.  The coolest part? Still no server-side scripts needed to make printing happen! A major design goal is to minimize server-side software in GeoMoose 3.0.  That means no more PHP requirement. There are two major roadblocks to that development:

 1. Buffering.  This still needs to be tackled.  The hope is to use a minified form of JSTS in order to provide client-side buffering of features.
 2. Printing. All of the previous print solutions in GeoMoose used server-side libraries for PHP or Perl.  Now, we are able to use jsPDF and some tricks with OpenLayers to generate a PDF on the client. Major victory!

GeoMoose 3.0 and npm
^^^^^^^^^^^^^^^^^^^^

GeoMoose 3.0 will also be available as a package on `npm <https://www.npmjs.org/>`_! Jim has been hard at work ensure that we have the project structured in such a way that folks can integrate the new GeoMoose into their npm-managed projects. It's not ready quite yet but will be for the first release.

See it all!
^^^^^^^^^^^

Printing is now available in the `Demo <https://demo.geomoose.org/3.0/>`_ and all the code is available on `GitHub <https://github.com/geomoose/gm3>`_.

4/18/2017 - Great things are afoot!
-----------------------------------


3.0 Development
^^^^^^^^^^^^^^^

Development on a fresh new GeoMoose 3.0 is getting really exciting! We've put together a great new architecture while working hard to keep GeoMoose familiar to users and administrators.  Check out the activity on `GitHub <https://github.com/geomoose/gm3>`_ and the new `Demo <https://demo.geomoose.org/3.0/>`_.


1/12/2017 - GeoMoose Version 2.9.2 Released
-------------------------------------------

GeoMoose 2.9.2 is a bug fix release that includes fixes for 2.9.1 and 2.9.2. (2.9.1 was never officially released).

See :ref:`2.9.1_Release` and :ref:`2.9.2_Release` for details.

5/19/2016 - GeoMoose Version 2.9.0 Released
-------------------------------------------

After months of hard work, we are pleased to bring you GeoMoose 2.9.0.

There were lots of new stuff and bug fixes for 2.9.0.

See :ref:`2.9.0_Release` for details.

10/2/2015 - GeoMoose Version 2.8.1 Released
-------------------------------------------

The GeoMoose project is excited to announce the 2.8.1 release!

The 2.8.1 release fixes bugs that were in 2.8.0.

Check the :ref:`2.8.1_Release` for more details.


6/20/2015 - GeoMoose Version 2.8.0 Released
-------------------------------------------

The GeoMoose project is excited to announce the 2.8.0 release!

2.8.0 fixes bugs that were in 2.7.1 and also includes some new exciting features.

Check the :ref:`2.8.0_Release` for more details.




11/12/2014 - GeoMoose Version 2.7.1 Released
--------------------------------------------

After few months of work, the GeoMoose project is excited to announce the 2.7.1 release!

2.7.1 is a bug fix release for 2.7 which means it should be better than 2.7 in every way.

Check the :ref:`2.7.1_Release` for more detail.

9/13/2014 - GeoMoose Version 2.7 Released
-----------------------------------------

After 18 months of work, the GeoMoose project is excited to announce the 2.7 release!

2.7 features major bug fixes in nearly every corner of the application. Version 2.7
should work with all 2.6 mapbooks and extensions.  This is a great set of upgrades
and ready for installation!

Check the :ref:`2.7_Release` for more detail. 

4/17/2013 - GeoMoose has graduated OSGeo Project Incubation
-----------------------------------------------------------
We are exited to announce that the GeoMoose project has graduated from 
OSGeo incubation.

4/6/2013 - Come see us at FOSS4G-NA 2013
---------------------------------------- 

Come visit us at `FOSS4G-NA 2013 <http://foss4g-na.org>`_ in Minneapolis, MN
from May 21-24.  GeoMoose started in Minnesota and was first presented in very
early form at OSG '05.  As OSG '05 was a precursor to the FOSS4G conferences,
we feel FOSS4G-NA 2013 is a homecoming for the project.  There will be a
`GeoMoose workshop <https://m360.mngislis.org/event/session.aspx?id=86848>`_
(presented as part of the `MN GIS/LIS Consortium's spring workshops
<https://m360.mngislis.org/event.aspx?eventID=76603>`_) in the afternoon on May
21st.  GeoMoose developers will be  attending the conference and we plan to
grab a table at the code sprint on Friday the 24th.  Friday is a free day, so
even if you can't attend the rest of the conference, stop by and see us during
the code sprint. Also, be sure to check out the other projects at the sprint
and the free presentations.

2/12/2013 - GeoMoose 2.6.1 Ready to Rumble
------------------------------------------
Many, many, bug fixes and enhancements to the GeoMoose 2.6 family! This is a very worthwhile download and smoothes out a number of the quirks with GeoMoose 2.6.  Check it out now! :ref:`download` and :ref:`2.6.1_Release` notes.

6/14/2012 - GeoMoose 2.6 Available for Download
-----------------------------------------------
Two months of testing completed, GeoMoose 2.6.0 is ready! Complete with Dojo integration and an updated OpenLayers!  :ref:`download` and :ref:`2.6_Release`  notes.

4/13/2012 - GeoMoose 2.6 RC1 Available Now
------------------------------------------
After nearly a year of development the new GeoMoose is here! The website has been updated with the new GeoMoose logo and the documentation is updating to include all of the new 2.6 features.  For some assistance on the differences between 2.4 and 2.6 please visit :ref:`2.6_Release` 

5/13/2011 - GeoMoose 2.4 Available Now!
---------------------------------------
Two months of testing completed, GeoMoose 2.4 is ready for download!  Check the downloads page for the latest updates!  :ref:`2.4_Release`


3/25/2011 - GeoMoose 2.4RC1 Ready for Download
----------------------------------------------
After over a year we have assembled the first release candidate for GeoMoose 2.4.  This integrates a lot of minor enhancements and fixes that have been contributed to the code, please download and test!



2/18/2010 - GeoMoose 2.2 Officially Released
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The official GeoMoose 2.2 Release has arrived!  This is the version is worth the upgrade from any 1.X series of GeoMoose installations.  View the full release notes: :doc:`../releases/2.2`.

2/3/2010 - NEW WEBSITE!
^^^^^^^^^^^^^^^^^^^^^^^
The new website is much improved:
 * We have live demos.
 * A new Gallery!
 * A new Trac ticketing system that allows any GeoMoose user to submit a ticket to GeoMoose developers.

2/3/2010 - GeoMoose 2.2 RC1 Released
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This is THE real 2.2 update.  This is the first RC, we will take another week for bugs to be filed in the new Trac system. View the :doc:`../releases/2.2` and check out all the new features!


10/9/2009 - GeoMoose 2.0.1 Released
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Great update! Download and Install! View The :doc:`../releases/2.0.1`.

8/20/2009 - Updated Documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
We've added some important new documentation.  UN*X installation instructions (for packages starting with 2.0.1) and a comprehensive list of configuration options that can be set in the mapbook.  Check 'em out!

7/21/2009 - GeoMoose 2.0 Released
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

GeoMoose 2.0 released! See downloads to get your copy.  Also, we've rolled out this shiny new website!

