
# Save result (Schema)

`ogc.openeo.processes.cubes.save_result` *v0.1*

Save processed data

[*Status*](http://www.opengis.net/def/status): Under development

## Description

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

## Examples

### Example 1
Calling `save_result` with these arguments returns `{"type": "Feature", "stac_version": "1.0.0", "id": "result-item", "geometry": null, "properties": {"datetime": "2020-01-01T00:00:00Z"}, "links": [], "assets": {}}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a minimal illustrative STAC Item, matching the `stac` shared type.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "format": "GTiff"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Save processed data
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  format:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/output-format/schema.yaml
  options:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/output-format-options/schema.yaml
required:
- data
- format

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/save_result/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/save_result/schema.yaml)

## Sources

* [OpenEO Processes — save_result](https://processes.openeo.org/#save_result)
* [Open-EO/openeo-processes — save_result.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/save_result.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/save_result`

