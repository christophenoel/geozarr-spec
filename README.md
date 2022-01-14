# GeoZarr-spec 0.1

This document aims to provides a geospatial extension to the Zarr specification (v2). Zarr specify a protocol and format used for storing Zarr arrays, while the extension defines **conventions** and recommendations for storing any **multidimensional georeferenced grid** of values (including rasters). 

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## Status

This specification is an early draft (v0.1)

## License

(CC BY 4.0) : Content in this repository is licensed under a Creative Commons Attribution 4.0 International  license. Licensees may copy, distribute, display, perform and make derivative works and remixes based on it only if they give the author or licensor the credits (attribution). You can find the complete text of this license at http://creativecommons.org/licenses/by/4.0/.

GeoZarr documentation by Christophe Noël (Spacebel) and other contributors.

## Conceptual Classes

### GeoZarr DataArray Variables

A GeoZarr DataArray variable is a **Zarr Array** that provides values of a measured or observed **phenomenon** (possibly indirectly computed using processing). For example, it provides the reflectance pixels of a captured satellite scene, or it describes the average vegetation index (NDVI) values for defined period of times.

GeoZarr DataArray variable MUST include the attribute **\_ARRAY_DIMENSIONS which list the dimension names** (this property was first introduced by xarray library).

"_ARRAY_DIMENSIONS": [
        "lat",
        "lon"
    ]
### GeoZarr Coordinates Variables

GeoZarr Coordinates variable is a one dimensional **Zarr Array** that **indexes a dimension** of a GeoZarr DataArray (e.g latitude, longitude, time, wavelength).

GeoZarr Coordinates variable MUST include the attribute **\_ARRAY_DIMENSIONS equal to the Zarr array name** (e.g. latitude for the latitude Zarr Array).

### GeoZarr Auxiliary Variables

GeoZarr Auxiliary variable is empty, one dimensional or multidimensional **Zarr Array** providing auxiliary information.

GeoZarr Auxiliary variable MUST include the attribute **\_ARRAY_DIMENSIONS set as an empty array**.

### GeoZarr Dataset

GeoZarr Dataset is a root **Zarr Group** which contains a consistent **set of DataArray variables** (observed data), **Coordinates variables**, Auxiliary variables, and optionally children Datasets (located in children Zarr Groups). 

GeoZarr Dataset MUST contain a consistent set of data for which the DataArray variables have aligned dimensions, share the same coordinates grid, and an equal spatial projection.

If multiple Array Variables share heterogenous dimensions or coordinates, a primary set MUST be located at root level, and the other sets put in children datasets.

## CF Conventions

GeoZarr Arrays and Coordinates Variables MUST include [Climate and Forecast CF](http://cfconventions.org/) conventions. The minimum set of attributes MUST be:

* standard_name for all variables
* grid_mapping for all array variables

A CF **standard name** is an attribute which identifies the physical quantity of a variable ([table](https://cfconventions.org/Data/cf-standard-names/78/build/cf-standard-name-table.html)). The quantity may describe the observed phenomenon for a DataArray (for example 'surface_bidirectional_reflectance' for optical sensor data) or identify the 

* grid_latitude, grid_longitude (spatial coordinates as degrees)
* projection_x_coordinate, projection_y_coordinates (spatial coordinates as per projection)
* sensor_band_identifier (multisptrectal band identifier)
* radiation_wavelength (hyperspectral wave length)

The **grid_mapping** variable defined by DataArray variable defines  the coordinate reference system (CRS) used for the horizontal spatial coordinate values. The grid_mapping value indicates the Auxliary variable that holds all the CF attribute describing the cRS. 

However, all other CF conventions are recommended, in particular the attributes below:

* add_offset
* scale_factor
* units (as per [UDUNITS v2](https://www.unidata.ucar.edu/software/udunits/udunits-2.2.28/udunits2.html))

### Multiscales

### Rechunking

###

## Specific Recommendations

### Multispectral Data

If the optical sensor captures spectral bands for different resolution, various structure might be considered:
* The root group holds the highest resolution dataset, and children groups the other resolutions.
* TBD

By the way, the spectral band itself might be represented in different maneer:
* If the band is represented in a dedicated array variable, As an array


