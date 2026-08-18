
# Any (Schema)

`ogc.openeo.processes.logic.any` *v0.1*

Is at least one value true?

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`any`](https://processes.openeo.org/#any) — *Is at least one value true?*. It models the `arguments` object of a process graph node invoking `any`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **any** (i.e. at least one) value in `data` is `true`. If no value is given (i.e. the array is empty) the process returns `false`.

By default all no-data values are ignored so that the process returns `true` if at least one value is true and `false` otherwise. Setting the `ignore_nodata` flag to `false` takes no-data values into account and the array values are reduced pairwise according to the following truth table:

```
        || no-data | false   | true
------- || ------- | ------- | ----
no-data || no-data | no-data | true
false   || no-data | false   | true
true    || true    | true    | true
```

**Remark:** The process evaluates all values in an arbitrary order and stops once the outcome is unambiguous, i.e. when either a `true` value is encountered, or when all values have been taken into account.

## Source

OpenEO Processes specification: [`any`](https://processes.openeo.org/#any) ([openeo-processes/any.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/any.json)).

## Examples

### Example 1
Calling `any` with these arguments returns `false`.
#### json
```json
{
  "data": [
    false,
    null
  ]
}
```


### Example 2
Calling `any` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true,
    null
  ]
}
```


### Example 3
Calling `any` with these arguments returns `null`.
#### json
```json
{
  "data": [
    false,
    null
  ],
  "ignore_nodata": false
}
```


### Example 4
Calling `any` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true,
    null
  ],
  "ignore_nodata": false
}
```


### Example 5
Calling `any` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true,
    false,
    true,
    false
  ]
}
```


### Example 6
Calling `any` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true,
    false
  ]
}
```


### Example 7
Calling `any` with these arguments returns `false`.
#### json
```json
{
  "data": [
    false,
    false
  ]
}
```


### Example 8
Calling `any` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true
  ]
}
```


### Example 9
Calling `any` with these arguments returns `null`.
#### json
```json
{
  "data": [
    null
  ],
  "ignore_nodata": false
}
```


### Example 10
Calling `any` with these arguments returns `false`.
#### json
```json
{
  "data": [
    null
  ]
}
```


### Example 11
Calling `any` with these arguments returns `false`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Is at least one value true?
type: object
properties:
  data:
    type: array
    items:
      type:
      - boolean
      - 'null'
  ignore_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/any/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/any/schema.yaml)

## Sources

* [OpenEO Processes — any](https://processes.openeo.org/#any)
* [Open-EO/openeo-processes — any.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/any.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/any`

