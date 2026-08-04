This Building Block proposes a schema representation of the OpenEO process [`save_result`](https://processes.openeo.org/#save_result) — *Save processed data*. It models the `arguments` object of a process graph node invoking `save_result`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Makes the processed data available in the given file format to the corresponding medium that is relevant for the context this processes is applied in:

* For **batch jobs** the data is stored on the back-end. STAC-compatible metadata is usually made available with the processed data.
* For **synchronous processing** the data is sent to the client as a direct response to the request.
* **Secondary web services** are provided with the processed data so that it can make use of it (e.g., visualize it). Web service may require the data in a certain format. Please refer to the documentation of the individual service types for details.

## Exceptions

- `FormatUnsuitable`: Data can't be transformed into the requested output format.
- `DataCubeEmpty`: The file format doesn't support storing empty data cubes.

## Source

OpenEO Processes specification: [`save_result`](https://processes.openeo.org/#save_result) ([openeo-processes/save_result.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/save_result.json)).
