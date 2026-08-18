
# Text concat (Schema)

`ogc.openeo.processes.texts.text_concat` *v0.1*

Concatenate elements to a single text

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`text_concat`](https://processes.openeo.org/#text_concat) — *Concatenate elements to a single text*. It models the `arguments` object of a process graph node invoking `text_concat`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Merges text representations (also known as *string*) of a set of elements to a single text, having the separator between each element.

## Source

OpenEO Processes specification: [`text_concat`](https://processes.openeo.org/#text_concat) ([openeo-processes/text_concat.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_concat.json)).

## Examples

### Example 1
Calling `text_concat` with these arguments returns `"Hello World"`.
#### json
```json
{
  "data": [
    "Hello",
    "World"
  ],
  "separator": " "
}
```


### Example 2
Calling `text_concat` with these arguments returns `"1234567890"`.
#### json
```json
{
  "data": [
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    0
  ]
}
```


### Example 3
Calling `text_concat` with these arguments returns `"null\ntrue\nfalse\n1\n-1.5\n\u00df"`.
#### json
```json
{
  "data": [
    null,
    true,
    false,
    1,
    -1.5,
    "\u00df"
  ],
  "separator": "\n"
}
```


### Example 4
Calling `text_concat` with these arguments returns `"210"`.
#### json
```json
{
  "data": [
    2,
    0
  ],
  "separator": 1
}
```


### Example 5
Calling `text_concat` with these arguments returns `""`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Concatenate elements to a single text
type: object
properties:
  data:
    type: array
    items:
      type:
      - string
      - number
      - boolean
      - 'null'
  separator:
    type:
    - string
    - number
    - boolean
    - 'null'
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_concat/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_concat/schema.yaml)

## Sources

* [OpenEO Processes — text_concat](https://processes.openeo.org/#text_concat)
* [Open-EO/openeo-processes — text_concat.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_concat.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/texts/text_concat`

