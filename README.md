# Load OSM to PostGIS on Mac

This is a quick illustration on importing Open Street Maps to PostGIS on Mac. At this stage it is assumed that PostgreSQL is installed in the Mac.

In the pgAdmin open script `Object> Scripts> CREATE Script` and run the following code to create a database called `OSM`;

`create database osm;`

`create extension postgis;`

