# GeoZarr-spec 0.1

This document aims to provides a geospatial extension to the Zarr specification (v2). Zarr specify a protocol and format used for storing Zarr arrays, while the extension defines **conventions** and recommendations for storing any **multidimensional georeferenced grid** of values (including rasters). 

GeoZarr baseline defines strict conventions that suits most use cases (and easily supported by libraries), but second GeoZarr+ model provides smoother recommendations for handling more complex scenarios. 

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## Status

This specification is an early draft (v0.1)

## License

GeoZarr documentation (c) by Christophe Noël (Spacebel) and other contributors.

Content in this repository is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license. Licensees may copy, distribute, display, perform and make derivative works and remixes based on it only if they give the author or licensor the credits (attribution). You can find the complete text of this license at http://creativecommons.org/licenses/by/4.0/.

## Geospatial Zarr Classes

### GeoZarr DataArray

A GeoZarr DataArray is a Zarr array which provides values of a measured/observed phenomenon (possibly indirectly computed using processing). For example, it provides the reflectance pixels of a captured satellite scene, or it describes the average vegetation index (NDVI) values for defined period of times.




### GeoZarr Dataset



"_ARRAY_DIMENSIONS": [
        "y",
        "x"
    ],


### GeoZarr Variable



Zarr Dataset 

###

## Structure

The structure of a geozarr is restricted to the following conditions:
* The single or multiple arrays holding values of the primary observed data MUST BE located in the root group (first level group) if the arrays have aligned dimensions and share the same coordinates grid.


__GeoZarr+__

If the arrays have aligned dimensions and share the same coordinates grid.
If the above recommendation is not satisfied (e.g. if the arrays don't share the same coordinates grid), then no array

## GeoZarr DataArray Attributes

The attribute \_ARRAY_DIMENSIONS list the dimension names (for example ["lat","lon"]).

### CF Conventions

### Multiscales

### Rechunking

###
