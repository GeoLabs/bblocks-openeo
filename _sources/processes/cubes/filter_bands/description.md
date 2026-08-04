This Building Block proposes a schema representation of the OpenEO process [`filter_bands`](https://processes.openeo.org/#filter_bands) — *Filter the bands by names*. It models the `arguments` object of a process graph node invoking `filter_bands`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the bands in the data cube so that bands that don't match any of the criteria are dropped from the data cube. The data cube is expected to have only one dimension of type `bands`. Fails with a `DimensionMissing` exception if no such dimension exists.

The following criteria can be used to select bands:

* `bands`: band name or common band name (e.g. `B01`, `B8A`, `red` or `nir`)
* `wavelengths`: ranges of wavelengths in micrometers (μm) (e.g. 0.5 - 0.6)

All these information are exposed in the band metadata of the collection. To keep algorithms interoperable it is recommended to prefer the common band names or the wavelengths over band names that are specific to the collection and/or back-end.

If multiple criteria are specified, any of them must match and not all of them, i.e. they are combined with an OR-operation. If no criteria are specified, the `BandFilterParameterMissing` exception must be thrown.

**Important:** The order of the specified array defines the order of the bands in the data cube, which can be important for subsequent processes. If multiple bands are matched by a single criterion (e.g. a range of wavelengths), they stay in the original order.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `BandFilterParameterMissing`: The process `filter_bands` requires any of the parameters `bands`, `common_names` or `wavelengths` to be set.
- `DimensionMissing`: A band dimension is missing.

## Source

OpenEO Processes specification: [`filter_bands`](https://processes.openeo.org/#filter_bands) ([openeo-processes/filter_bands.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_bands.json)).
