# measures-cetb-file-description
This repository contains descriptions of our MEaSUREs CETB files, for comment and review by our project Early Adopters.

## Requirements

* Our output file definition will be acceptable for NSIDC DAAC to easily ingest our data set into ECS.
* We aim to keep file size maximum of 1 GB (larger files are allowed, but network speeds still aren't what they should be).
* We will follow netCDF-CF 1.6 conventions for all but the requirement that puts the lat/lon arrays into the file.
* Our output files will pass CF-compliance-checking for all but the lat/lon arrays.   We will use Ed Armstrong's tool at JPL for compliance-checking.
* Each CETB file will contain 1 TB array variable, with associated ancillary variables according to gridding technique (1 TB grid per file).  We may have a practical limit on the number of ancillary variables to include, limited by maximum file size.
* Each CETB file of the same type (projection, GRD, SIR, BGI) will contain the same file-level metadata.
* We will follow the DRY (Don't Repeat Yourself) principle: Metadata will not be duplicated at multiple places in the same file. One exception to this will be for time values which will be machine- and human-readable.
* Variable/attribute names will be CF-compliant whenever possible.
* Data arrays in our NetCDF files will be convertible to geoTIFF format using standard GDAL command-line utilities.

## Filenaming Convention

CETB filenames will be:

<grid_name>.<sensor_platform>...nc

