# Readme - GeoZarr-Spec

GeoZarr Spec aims to provides a geospatial extension to the Zarr specification (v2). Zarr specifies a protocol and format used for storing Zarr arrays, while the present extension defines **conventions** and recommendations for storing **multidimensional georeferenced grid** of geospatial observations (including rasters). 

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## Document and Resources

Specification [document](geozarr-spec.md) - [Change Log](https://github.com/christophenoel/geozarr-spec/wiki)

Demonstration Videos ([Youtube channel](https://youtube.com/playlist?list=PLzPGC4s5HQOPdeLoK1MXK6gEa1x2Az8Dn):
- [Hyperspectral Data Store and Access Project](https://youtu.be/CfmPppVR-o4)
- [GeoZarr Visual Portrayals and OpenLayers extension](https://youtu.be/IKURmv6CVGU)
- [GeoZarr Fast Time Series Plotting](https://youtu.be/Nt1URJqW71o)
- [GeoZarr Compute and plot NDWI index at runtime](https://youtu.be/UP0DjphdZgM)
- [GeoZarr Serverless Visualisation and Pixel-Based Access](https://youtu.be/sKlejJcPKqQ)
- [GeoZarr vs COG Performances](https://youtu.be/KGC8mLqlsCs)
- Advanced applications: coming soon

## Status

This specification is an early draft deveveloped in the frame of an European Space Agency (ESA) GSTP. Through the optional General Support Technology Programme (GSTP) ESA, Participating States and Industry work together to convert promising engineering concepts into a broad spectrum of useable products.

## Changelog

### v0.4 

* Added visual portrayals and symbology (instead of quicklook)
* Specified default multiscale non-projection (pseudo 'Plate Carree')

### v0.3

* Refined multiscales metadata (crs and level attributes)

### v0.2

* Specified multiscales zoom level str

## License

(CC BY 4.0) : Content in this repository is licensed under a Creative Commons Attribution 4.0 International  license. Licensees may copy, distribute, display, perform and make derivative works and remixes based on it only if they give the author or licensor the credits (attribution). You can find the complete text of this license at http://creativecommons.org/licenses/by/4.0/.

GeoZarr documentation by Christophe Noël from Spacebel, supported by ScanWorld and other contributors.
