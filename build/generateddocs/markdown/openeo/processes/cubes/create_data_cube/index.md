
# Create data cube (Schema)

`ogc.openeo.processes.cubes.create_data_cube` *v0.1*

Create an empty data cube

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`create_data_cube`](https://processes.openeo.org/#create_data_cube) — *Create an empty data cube*. It models the `arguments` object of a process graph node invoking `create_data_cube`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Creates a new data cube without dimensions. Dimensions can be added with `add_dimension()`.

## Source

OpenEO Processes specification: [`create_data_cube`](https://processes.openeo.org/#create_data_cube) ([openeo-processes/create_data_cube.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/create_data_cube.json)).

## Examples

### Example 1
Calling `create_data_cube` with these arguments returns `{}`.

Takes no parameters; always returns a new, empty data cube.
#### json
```json
{}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Create an empty data cube
type: object
properties: {}

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/create_data_cube/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/create_data_cube/schema.yaml)

## Sources

* [OpenEO Processes — create_data_cube](https://processes.openeo.org/#create_data_cube)
* [Open-EO/openeo-processes — create_data_cube.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/create_data_cube.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/create_data_cube`

