
# Text begins (Schema)

`ogc.openeo.processes.texts.text_begins` *v0.1*

Text begins with another text

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`text_begins`](https://processes.openeo.org/#text_begins) — *Text begins with another text*. It models the `arguments` object of a process graph node invoking `text_begins`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the text (also known as *string*) specified for `data` contains the text specified for `pattern` at the beginning. No-data values are passed through.

## Source

OpenEO Processes specification: [`text_begins`](https://processes.openeo.org/#text_begins) ([openeo-processes/text_begins.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_begins.json)).

## Examples

### Example 1
Calling `text_begins` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "amet"
}
```


### Example 2
Calling `text_begins` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "Lorem"
}
```


### Example 3
Calling `text_begins` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "lorem"
}
```


### Example 4
Calling `text_begins` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "lorem",
  "case_sensitive": false
}
```


### Example 5
Calling `text_begins` with these arguments returns `true`.
#### json
```json
{
  "data": "\u00c4",
  "pattern": "\u00e4",
  "case_sensitive": false
}
```


### Example 6
Calling `text_begins` with these arguments returns `null`.
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
description: Text begins with another text
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_begins/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_begins/schema.yaml)

## Sources

* [OpenEO Processes — text_begins](https://processes.openeo.org/#text_begins)
* [Open-EO/openeo-processes — text_begins.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_begins.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/texts/text_begins`

