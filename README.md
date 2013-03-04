personal
========

This repo is in order to check commits before merging work.  This work was done to resolve the missing geocode 
information for foreign countries.

Issues: xml files being processed use ISO 3166 country codes.  gnsloc table uses FIPS 10-4 country codes. Additionally,
gnsloc table only storing country codes as far as CH, ie table incomplete.

Created crosswalk table between FIPS 10-4 country codes and ISO 3166 country codes. Table named countryCodes in 
loctbl.sqlite3 

Recreated gnsloc table from GNA website.   Added a new column to gnsloc, namely CC1_FIPS, to store (back-up) the 
values of CC1.  Then loaded ISO 3166 country codes into CC1 from "countryCodes" crosswalk table.

The loctbl.sqlite3 file is stored locally in /Users/jill/Development/Berkeley/ERSO/PatentProject/patentdata.
There is a symbolic link to this file, loctbl, in /Users/jill/git/patentprocessor
lrwxr-xr-x  1 jill  staff  77 Jan 15 22:10 loctbl -> /Users/jill/Development/Berkeley/ERSO/PatentProject/patentdata/loctbl.sqlite3

loctbl.sqlite3 will have to be copied to the server once this has been tested, and copied locally onto everyone's 
machine, to replace their current loctbl.sqlite3 being used. 
