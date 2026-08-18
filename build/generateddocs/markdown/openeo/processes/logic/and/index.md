
# And (Schema)

`ogc.openeo.processes.logic.and` *v0.1*

Logical AND

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`and`](https://processes.openeo.org/#and) — *Logical AND*. It models the `arguments` object of a process graph node invoking `and`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **both** values are true.

Evaluates parameter `x` before `y` and stops once the outcome is unambiguous. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false | true
------- || ------- | ----- | -------
no-data || no-data | false | no-data
false   || false   | false | false
true    || no-data | false | true
```

## Source

OpenEO Processes specification: [`and`](https://processes.openeo.org/#and) ([openeo-processes/and.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/and.json)).

## Examples

### Example 1
Calling `and` with these arguments returns `true`.
#### json
```json
{
  "x": true,
  "y": true
}
```


### Example 2
Calling `and` with these arguments returns `false`.
#### json
```json
{
  "x": true,
  "y": false
}
```


### Example 3
Calling `and` with these arguments returns `false`.
#### json
```json
{
  "x": false,
  "y": false
}
```


### Example 4
Calling `and` with these arguments returns `false`.
#### json
```json
{
  "x": false,
  "y": null
}
```


### Example 5
Calling `and` with these arguments returns `null`.
#### json
```json
{
  "x": true,
  "y": null
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Logical AND
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/and/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/and/schema.yaml)

## Sources

* [OpenEO Processes — and](https://processes.openeo.org/#and)
* [Open-EO/openeo-processes — and.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/and.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/and`

