siguanet-dbdemo
===============

Python based command-line tool for setting up a SIGUANET geodatabase with demo data

## What's SIGUANET?
SIGUANET is a free software project that aims to share the University of Alicante's corporate built asset management technology (SIGUA) with the developers community.
In this sense, SIGUANET will hopefully be useful for other universities and academic organizations.

## What's siguanet-dbdemo
This is a command-line tool that helps DBAs to set-up an existing PostgreSQL/PostGIS database as a SIGUANET database and populate it with some demo data.
This includes dummy data for three campuses with several buildings where rooms are classified according to uses and departments, and employees localized.
The `siguanet-dbdemo` command provides a simple interface which can be localized using gettext. Presently only english and spanish languages are available. Instructions on localization can be found into the `locale\` folder.

### Database requirements
Please, bear in mind this tool won't create a database for you. A clean PostGIS database is needed which meets the following requirements:
* PostgreSQL 9.2 or greater
* PostGIS 2.0 or greater

Remember that, beginning with version 2.0, PostGIS is installed as an extension on a per-database basis, thus making the management of geodatabases much cleaner.

### Python requirements
This Python script has been tested on both, Python 2.7 and Python 3.2 environments on Linux boxes.
It makes use of some libraries which may or may not be present in your distribution. Please ensure you have the following python modules installed:
* mako
* psycopg2

## How does it work?
The `siguanet-dbdemo` command requires the user to provide connection parameters to a PostgreSQL database.
In its simplest form, you can invoke the command like this:

`siguanet-dbdemo.py -d yourdbname -u yourusername`

Once you provide your PostgreSQL account password, this will create all SIGUANET objects on `yourdatabase` at your `localhost`.
The database will be subsequently populated with departments, employees and room geometries using `srid=25830`.

Execute `-h` option for information on all options.
