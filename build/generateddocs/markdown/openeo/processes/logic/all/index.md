
# All (Schema)

`ogc.openeo.processes.logic.all` *v0.1*

Are all of the values true?

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`all`](https://processes.openeo.org/#all) — *Are all of the values true?*. It models the `arguments` object of a process graph node invoking `all`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **all** of the values in `data` are true. If no value is given (i.e. the array is empty) the process returns `true`.

By default, all no-data values are ignored so that the process returns `true` if all values are no-data or true, and `false` otherwise. Setting the `ignore_nodata` flag to `false` takes no-data values into account and the array values are reduced pairwise according to the following truth table:

```
        || no-data | false | true
------- || ------- | ----- | -------
no-data || no-data | false | no-data
false   || false   | false | false
true    || no-data | false | true
```

**Remark:** The process evaluates all values in an arbitrary order and stops once the outcome is unambiguous, i.e. when either a `false` value is encountered, or when all values have been taken into account.

## Source

OpenEO Processes specification: [`all`](https://processes.openeo.org/#all) ([openeo-processes/all.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/all.json)).

## Examples

### Example 1
Calling `all` with these arguments returns `false`.
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
Calling `all` with these arguments returns `true`.
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
Calling `all` with these arguments returns `false`.
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
Calling `all` with these arguments returns `null`.
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
Calling `all` with these arguments returns `false`.
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
Calling `all` with these arguments returns `false`.
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
Calling `all` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true,
    true
  ]
}
```


### Example 8
Calling `all` with these arguments returns `true`.
#### json
```json
{
  "data": [
    true
  ]
}
```


### Example 9
Calling `all` with these arguments returns `null`.
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
Calling `all` with these arguments returns `true`.
#### json
```json
{
  "data": [
    null
  ]
}
```


### Example 11
Calling `all` with these arguments returns `true`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Are all of the values true?
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/all/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/all/schema.yaml)

## Sources

* [OpenEO Processes — all](https://processes.openeo.org/#all)
* [Open-EO/openeo-processes — all.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/all.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/all`

