
# Is nodata (Schema)

`ogc.openeo.processes.comparison.is_nodata` *v0.1*

Value is a no-data value

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`is_nodata`](https://processes.openeo.org/#is_nodata) — *Value is a no-data value*. It models the `arguments` object of a process graph node invoking `is_nodata`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the specified data is no-data value, i.e. equals to any of the no-data values of the data cube (or `null`). The specific no-data values are usually provided through the collection or STAC metadata.

The special numerical value `NaN` (not a number) as defined by the [IEEE Standard 754](https://ieeexplore.ieee.org/document/4610935) is only considered as no-data value if explicitly specified as no-data value for the data cube.

## Source

OpenEO Processes specification: [`is_nodata`](https://processes.openeo.org/#is_nodata) ([openeo-processes/is_nodata.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nodata.json)).

## Examples

### Example 1
Calling `is_nodata` with these arguments returns `false`.
#### json
```json
{
  "x": 1
}
```


### Example 2
Calling `is_nodata` with these arguments returns `false`.
#### json
```json
{
  "x": "Test"
}
```


### Example 3
Calling `is_nodata` with these arguments returns `true`.
#### json
```json
{
  "x": null
}
```


### Example 4
Calling `is_nodata` with these arguments returns `false`.
#### json
```json
{
  "x": [
    null,
    null
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Value is a no-data value
type: object
properties:
  x:
    description: Any data type is allowed.
required:
- x

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_nodata/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/is_nodata/schema.yaml)

## Sources

* [OpenEO Processes — is_nodata](https://processes.openeo.org/#is_nodata)
* [Open-EO/openeo-processes — is_nodata.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/is_nodata.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/is_nodata`

