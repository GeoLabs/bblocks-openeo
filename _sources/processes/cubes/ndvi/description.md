This Building Block proposes a schema representation of the OpenEO process [`ndvi`](https://processes.openeo.org/#ndvi) — *Normalized Difference Vegetation Index*. It models the `arguments` object of a process graph node invoking `ndvi`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the Normalized Difference Vegetation Index (NDVI). The NDVI is computed as *`(nir - red) / (nir + red)`*.

The `data` parameter expects a raster data cube with a dimension of type `bands` or a `DimensionAmbiguous` exception is thrown otherwise. By default, the dimension must have at least two bands with the common names `red` and `nir` assigned. Otherwise, the user has to specify the parameters `nir` and `red`. If neither is the case, either the exception `NirBandAmbiguous` or `RedBandAmbiguous` is thrown. The common names for each band are specified in the collection's band metadata and are *not* equal to the band names.

By default, the dimension of type `bands` is dropped by this process. To keep the dimension specify a new band name in the parameter `target_band`. This adds a new dimension label with the specified name to the dimension, which can be used to access the computed values. If a band with the specified name exists, a `BandExists` is thrown.

This process is very similar to the process `normalized_difference()`, but determines the bands automatically based on the common names (`red`/`nir`) specified in the metadata.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `spatial` (axis=['x', 'y']), per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `NirBandAmbiguous`: The NIR band can't be resolved, please specify the specific NIR band name.
- `RedBandAmbiguous`: The red band can't be resolved, please specify the specific red band name.
- `DimensionAmbiguous`: dimension of type `bands` is not available or is ambiguous..
- `BandExists`: A band with the specified target name exists.

## Source

OpenEO Processes specification: [`ndvi`](https://processes.openeo.org/#ndvi) ([openeo-processes/ndvi.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/ndvi.json)).
