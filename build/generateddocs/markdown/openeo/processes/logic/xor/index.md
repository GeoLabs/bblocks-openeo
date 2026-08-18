
# Xor (Schema)

`ogc.openeo.processes.logic.xor` *v0.1*

Logical XOR (exclusive or)

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`xor`](https://processes.openeo.org/#xor) — *Logical XOR (exclusive or)*. It models the `arguments` object of a process graph node invoking `xor`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **exactly one** of the values is true. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false   | true
------- || ------- | ------- | -------
no-data || no-data | no-data | no-data
false   || no-data | false   | true
true    || no-data | true    | false
```

## Source

OpenEO Processes specification: [`xor`](https://processes.openeo.org/#xor) ([openeo-processes/xor.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/xor.json)).

## Examples

### Example 1
Calling `xor` with these arguments returns `false`.
#### json
```json
{
  "x": true,
  "y": true
}
```


### Example 2
Calling `xor` with these arguments returns `false`.
#### json
```json
{
  "x": false,
  "y": false
}
```


### Example 3
Calling `xor` with these arguments returns `true`.
#### json
```json
{
  "x": true,
  "y": false
}
```


### Example 4
Calling `xor` with these arguments returns `null`.
#### json
```json
{
  "x": true,
  "y": null
}
```


### Example 5
Calling `xor` with these arguments returns `null`.
#### json
```json
{
  "x": false,
  "y": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Logical XOR (exclusive or)
type: object
properties:
  x:
    type:
    - boolean
    - 'null'
  y:
    type:
    - boolean
    - 'null'
required:
- x
- y

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/xor/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/xor/schema.yaml)

## Sources

* [OpenEO Processes — xor](https://processes.openeo.org/#xor)
* [Open-EO/openeo-processes — xor.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/xor.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/xor`

