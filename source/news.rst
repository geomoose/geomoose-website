GeoMoose News
=============

8/18/2023 - GeoMoose 3.12.0 Released
------------------------------------
Cool new measure tool, oh, and some fixes. See :ref:`3.12.0_Release` for details.

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


:doc:`info/old_news`

.. Silence not in toctree warnings for toolbar/main page linked pages
.. toctree::
  :hidden:

  info/old_news
