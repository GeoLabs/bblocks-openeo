This Building Block proposes a schema representation of the OpenEO process [`load_collection`](https://processes.openeo.org/#load_collection) — *Load a collection*. It models the `arguments` object of a process graph node invoking `load_collection`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Loads a collection from the current back-end by its id and returns it as a processable data cube. The data that is added to the data cube can be restricted with the parameters `spatial_extent`, `temporal_extent`, `bands` and `properties`. If no data is available for the given extents, a `NoDataAvailable` exception is thrown.

**Remarks:**

* All dimensions that specify nominal dimension labels (e.g. bands) are ordered as specified in the data cube metadata (`cube:dimensions`) unless otherwise specified in a corresponding parameter (e.g. `bands`).
* If no additional parameter is specified this would imply that the whole data set is expected to be loaded. Due to the large size of many data sets, this is not recommended and may be optimized by back-ends to only load the data that is actually required after evaluating subsequent processes such as filters. This means that the values in the data cube should be processed only after the data has been limited to the required extent and as a consequence also to a manageable size.
* The scale and offset are not applied automatically when loading the data. If the corresponding STAC properties are present in the collection metadata, they need to be applied explicitly in the UDP.

## Data cube dimension requirements

- `spatial_extent` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `NoDataAvailable`: There is no data available for the given extents.
- `TemporalExtentEmpty`: The temporal extent is empty. The second instant in time must always be greater/later than the first instant in time.

## Source

OpenEO Processes specification: [`load_collection`](https://processes.openeo.org/#load_collection) ([openeo-processes/load_collection.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/load_collection.json)).
