# GeoZarr-spec 0.1

This document aims to provides a geospatial extension to the Zarr (v2) specification. Zarr specify a protocol and format used for storing Zarr arrays. 

The extension defines conventions and recommendations for storing any multidimensional georeferenced grid of values (including rasters). The baseline extension defines

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## Status

This specification is a very early draft (v0.1)

## Geospatial Zarr Classes

### GeoZarr Dataset

### GeoZarr DataArray

### GeoZarr Variable

Zarr Dataset 

###

## Structure

The structure of a geozarr is restricted to the following conditions:
* The single or multiple arrays holding values of the primary observed data MUST BE located in the root group (first level group) if the arrays have aligned dimensions and share the same coordinates grid.


*GeoZarr+*

If the above recommendation is not satisfied (e.g. if the arrays don't share the same coordinates grid), then no array

## Observed Data Attributes

### CF Conventions

### Multiscales

### Rechunking

###
