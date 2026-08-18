
# Array create (Schema)

`ogc.openeo.processes.arrays.array_create` *v0.1*

Create an array

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`array_create`](https://processes.openeo.org/#array_create) — *Create an array*. It models the `arguments` object of a process graph node invoking `array_create`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Creates a new array, which by default is empty.

The second parameter `repeat` allows to add the given array multiple times to the new array.

In most cases you can simply pass a (native) array to processes directly, but this process is especially useful to create a new array that is getting returned by a child process, for example in `apply_dimension()`.

## Source

OpenEO Processes specification: [`array_create`](https://processes.openeo.org/#array_create) ([openeo-processes/array_create.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_create.json)).

## Examples

### Example 1
Calling `array_create` with these arguments returns `[]`.
#### json
```json
{}
```


### Example 2
Calling `array_create` with these arguments returns `["this", "is", "a", "test"]`.
#### json
```json
{
  "data": [
    "this",
    "is",
    "a",
    "test"
  ]
}
```


### Example 3
Calling `array_create` with these arguments returns `[null, null, null]`.
#### json
```json
{
  "data": [
    null
  ],
  "repeat": 3
}
```


### Example 4
Calling `array_create` with these arguments returns `[1, 2, 3, 1, 2, 3]`.
#### json
```json
{
  "data": [
    1,
    2,
    3
  ],
  "repeat": 2
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Create an array
type: object
properties:
  data:
    type: array
    items:
      description: Any data type is allowed.
  repeat:
    type: integer
    minimum: 1

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_create/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/arrays/array_create/schema.yaml)

## Sources

* [OpenEO Processes — array_create](https://processes.openeo.org/#array_create)
* [Open-EO/openeo-processes — array_create.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_create.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/arrays/array_create`

