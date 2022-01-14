# GeoZarr-spec 0.1

This document aims to provides a geospatial extension to the Zarr specification (v2). Zarr specify a protocol and format used for storing Zarr arrays, while the extension defines **conventions** and recommendations for storing any **multidimensional georeferenced grid** of values (including rasters). 

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## Status

This specification is an early draft (v0.1)

## License

GeoZarr documentation (c) by Christophe Noël (Spacebel) and other contributors.

Content in this repository is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license. Licensees may copy, distribute, display, perform and make derivative works and remixes based on it only if they give the author or licensor the credits (attribution). You can find the complete text of this license at http://creativecommons.org/licenses/by/4.0/.

## GeoZarr Classes

### GeoZarr DataArray

A GeoZarr DataArray is a **Zarr Array** that provides values of a measured or observed **phenomenon** (possibly indirectly computed using processing). For example, it provides the reflectance pixels of a captured satellite scene, or it describes the average vegetation index (NDVI) values for defined period of times.

GeoZarr DataArray MUST include the attribute **\_ARRAY_DIMENSIONS which list the dimension names**.

"_ARRAY_DIMENSIONS": [
        "lat",
        "lon"
    ]
### GeoZarr Coordinates Variable

GeoZarr Coordinates Variable is a one dimensional **Zarr Array** that **indexes a dimension** of a GeoZarr DataArray (e.g latitude, longitude, time, wavelength).

GeoZarr Coordinates Variable MUST include the attribute **\_ARRAY_DIMENSIONS equal to the Zarr array name** (e.g. latitude for the latitude Zarr Array).

### GeoZarr Auxiliary Variable

GeoZarr Auxiliary Variable is multidimensional **Zarr Array** providing auxiliary information. This includes geospatial metadata such as grid_mapping which describe the projection of the coordinates.

GeoZarr Auxiliary Variable MUST include the attribute **\_ARRAY_DIMENSIONS set as an empty array**.

### GeoZarr Dataset

GeoZarr Dataset is a root **Zarr Group** which contains a consistent **set of DataArrays** (observed data), coordinates, auxiliary variables, and optionally children groups.

GeoZarr Dataset MUST contain a consistent set of data for which the DataArrays have aligned dimensions and share the same coordinates grid. If multiple arrays share heterogenous dimensions or coordinates, a primary set MUST be located at root level, and the other sets put in children Zarr groups.

## GEoZarr - CF Conventions

### Multiscales

### Rechunking

###
