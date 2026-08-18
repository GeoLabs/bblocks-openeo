
# Text contains (Schema)

`ogc.openeo.processes.texts.text_contains` *v0.1*

Text contains another text

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`text_contains`](https://processes.openeo.org/#text_contains) — *Text contains another text*. It models the `arguments` object of a process graph node invoking `text_contains`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the text (also known as *string*) specified for `data` contains the text specified for `pattern`. No-data values are passed through.

## Source

OpenEO Processes specification: [`text_contains`](https://processes.openeo.org/#text_contains) ([openeo-processes/text_contains.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_contains.json)).

## Examples

### Example 1
Calling `text_contains` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "openEO"
}
```


### Example 2
Calling `text_contains` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "ipsum dolor"
}
```


### Example 3
Calling `text_contains` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "Ipsum Dolor"
}
```


### Example 4
Calling `text_contains` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "SIT",
  "case_sensitive": false
}
```


### Example 5
Calling `text_contains` with these arguments returns `true`.
#### json
```json
{
  "data": "\u00c4\u00d6\u00dc",
  "pattern": "\u00f6",
  "case_sensitive": false
}
```


### Example 6
Calling `text_contains` with these arguments returns `null`.
#### json
```json
{
  "data": null,
  "pattern": "null"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Text contains another text
type: object
properties:
  data:
    type:
    - string
    - 'null'
  pattern:
    type: string
  case_sensitive:
    type: boolean
required:
- data
- pattern

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_contains/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_contains/schema.yaml)

## Sources

* [OpenEO Processes — text_contains](https://processes.openeo.org/#text_contains)
* [Open-EO/openeo-processes — text_contains.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_contains.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/texts/text_contains`

