
# Or (Schema)

`ogc.openeo.processes.logic.or` *v0.1*

Logical OR

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`or`](https://processes.openeo.org/#or) — *Logical OR*. It models the `arguments` object of a process graph node invoking `or`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **at least one** of the values is true. Evaluates parameter `x` before `y` and stops once the outcome is unambiguous. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false   | true
------- || ------- | ------- | ----
no-data || no-data | no-data | true
false   || no-data | false   | true
true    || true    | true    | true
```

## Source

OpenEO Processes specification: [`or`](https://processes.openeo.org/#or) ([openeo-processes/or.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/or.json)).

## Examples

### Example 1
Calling `or` with these arguments returns `true`.
#### json
```json
{
  "x": true,
  "y": true
}
```


### Example 2
Calling `or` with these arguments returns `false`.
#### json
```json
{
  "x": false,
  "y": false
}
```


### Example 3
Calling `or` with these arguments returns `true`.
#### json
```json
{
  "x": true,
  "y": null
}
```


### Example 4
Calling `or` with these arguments returns `true`.
#### json
```json
{
  "x": null,
  "y": true
}
```


### Example 5
Calling `or` with these arguments returns `null`.
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
description: Logical OR
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/or/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/or/schema.yaml)

## Sources

* [OpenEO Processes — or](https://processes.openeo.org/#or)
* [Open-EO/openeo-processes — or.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/or.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/or`

