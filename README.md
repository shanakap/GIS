# Load OSM to PostGIS on Mac

This is a quick illustration on importing Open Street Maps to PostGIS on Mac. At this stage it is assumed that PostgreSQL is installed in the Mac.

### Step 1
In the pgAdmin open script `Object> Scripts> CREATE Script` and run the following code to create a database called `OSM`;
```
create database osm;
create extension postgis;
```

### Step 2

Open terminal and install osmosis

`brew install osmosis`

### Step 3

Now run the following to import osm to the postgis database;

`Shanakas-MBP:~ postgres$ osm2pgsql -c -d osm -U "postgres" -W -H "localhost" -P 5432 /Data/england.osh.pbf` 

You will be asked to enter the password of PostgreSQL. 

If you get the following error,

```
Node cache size is too small to fit all nodes. Please increase cache size
Error occurred, cleaning up
```
Increase the cache by `-C`

`
Shanakas-MBP:~ postgres$ osm2pgsql -c -d osm -U "postgres" -W -H "localhost" -P 5432 -C 3000 /Data/england.osh.pbf 
`
