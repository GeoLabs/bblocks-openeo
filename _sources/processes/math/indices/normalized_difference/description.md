This Building Block proposes a schema representation of the OpenEO process [`normalized_difference`](https://processes.openeo.org/#normalized_difference) — *Normalized difference*. It models the `arguments` object of a process graph node invoking `normalized_difference`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the normalized difference for two bands. The normalized difference is computed as *`(x - y) / (x + y)`*.

This process could be used for a number of remote sensing indices such as:

* [NDVI](https://eos.com/ndvi/): `x` = NIR band, `y` = red band
* [NDWI](https://eos.com/ndwi/): `x` = NIR band, `y` = SWIR band
* [NDSI](https://eos.com/ndsi/): `x` = green band, `y` = SWIR band

Some back-ends may have native processes such as `ndvi()` available for convenience.

## Source

OpenEO Processes specification: [`normalized_difference`](https://processes.openeo.org/#normalized_difference) ([openeo-processes/normalized_difference.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/normalized_difference.json)).
