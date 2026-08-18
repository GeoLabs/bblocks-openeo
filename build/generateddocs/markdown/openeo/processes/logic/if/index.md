
# If (Schema)

`ogc.openeo.processes.logic.if` *v0.1*

If-Then-Else conditional

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`if`](https://processes.openeo.org/#if) — *If-Then-Else conditional*. It models the `arguments` object of a process graph node invoking `if`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

If the value passed is `true`, returns the value of the `accept` parameter, otherwise returns the value of the `reject` parameter.

This is basically an if-then-else construct as in other programming languages.

## Source

OpenEO Processes specification: [`if`](https://processes.openeo.org/#if) ([openeo-processes/if.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/if.json)).

## Examples

### Example 1
Calling `if` with these arguments returns `"A"`.
#### json
```json
{
  "value": true,
  "accept": "A",
  "reject": "B"
}
```


### Example 2
Calling `if` with these arguments returns `"B"`.
#### json
```json
{
  "value": null,
  "accept": "A",
  "reject": "B"
}
```


### Example 3
Calling `if` with these arguments returns `[4, 5, 6]`.
#### json
```json
{
  "value": false,
  "accept": [
    1,
    2,
    3
  ],
  "reject": [
    4,
    5,
    6
  ]
}
```


### Example 4
Calling `if` with these arguments returns `123`.
#### json
```json
{
  "value": true,
  "accept": 123
}
```


### Example 5
Calling `if` with these arguments returns `null`.
#### json
```json
{
  "value": false,
  "accept": 1
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: If-Then-Else conditional
type: object
properties:
  value:
    type:
    - boolean
    - 'null'
  accept:
    description: Any data type is allowed.
  reject:
    description: Any data type is allowed.
required:
- value
- accept

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/if/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/logic/if/schema.yaml)

## Sources

* [OpenEO Processes — if](https://processes.openeo.org/#if)
* [Open-EO/openeo-processes — if.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/if.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/logic/if`

