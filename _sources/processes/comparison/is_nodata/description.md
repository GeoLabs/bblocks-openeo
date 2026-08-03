This Building Block proposes a schema representation of the OpenEO process [`is_nodata`](https://processes.openeo.org/#is_nodata) — *Value is a no-data value*. It models the `arguments` object of a process graph node invoking `is_nodata`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified data is no-data value, i.e. equals to any of the no-data values of the data cube (or `null`). The specific no-data values are usually provided through the collection or STAC metadata.

The special numerical value `NaN` (not a number) as defined by the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935) is only considered as no-data value if explicitly specified as no-data value for the data cube.

## Source

OpenEO Processes specification: [`is_nodata`](https://processes.openeo.org/#is_nodata) ([openeo-processes/is_nodata.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nodata.json)).
