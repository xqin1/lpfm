lpfm
====

creating the low power FM map

What Problem this Solves
------------------------
Low Power FM (LPFM) is an opportunity for local users to start their own broadcasting stations on unused frequencies in their area.  Currently the rules around LPFM are difficult to visualize.

How this Project Solves this Problem
------------------------------------
This project takes all of the towers broadcasting all of the FM stations, and with their attributes and associated protection rules, creates the landscape of opportunities for Low Power FM.  That is, it creates the map of which channels are open where given the current landscape of protected stations.

Requirements
------------
The end goal is that output maintains the (1) total number of excluded channels at all spaces - the total field -  (2) each excluded channel at all spaces - c<number> field - and (3) and all polygons as simple, single geometries (e.g. no overlapping, no multipart).

Files
------
- lpfm.py - primary code to develop the output polygons 
- *.shp - primary shape file containing exclusion areas of all station 
		(found here - https://dl.dropbox.com/u/40278130/lpfm_all_buffers.zip)

Dependencies
------------
- PostGIS (using OpenGeo Suite)
- psycopg (python library for PostgresSQL - http://www.initd.org/psycopg/)
- ArcGIS (for the union step_

Folders
-------
- processing - contains the procesisng steps
- visualization - contains the visualization steps

Problems 
--------
am having problems w/ st_union throwing errors on node intersections; there are of course tons of slivers and the like, which i try to mitigate for.
using the input shapes (test and test1 work fine, but the co shape throws an error at record 81 in the loop.  look at the <schema>.working for the resulting

the resulting script needs to run on 38,000 polygons nationwide