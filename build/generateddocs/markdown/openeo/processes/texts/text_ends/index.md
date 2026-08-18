
# Text ends (Schema)

`ogc.openeo.processes.texts.text_ends` *v0.1*

Text ends with another text

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`text_ends`](https://processes.openeo.org/#text_ends) — *Text ends with another text*. It models the `arguments` object of a process graph node invoking `text_ends`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks whether the text (also known as *string*) specified for `data` contains the text specified for `pattern` at the end. No-data values are passed through.

## Source

OpenEO Processes specification: [`text_ends`](https://processes.openeo.org/#text_ends) ([openeo-processes/text_ends.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_ends.json)).

## Examples

### Example 1
Calling `text_ends` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "amet"
}
```


### Example 2
Calling `text_ends` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "AMET"
}
```


### Example 3
Calling `text_ends` with these arguments returns `false`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "Lorem"
}
```


### Example 4
Calling `text_ends` with these arguments returns `true`.
#### json
```json
{
  "data": "Lorem ipsum dolor sit amet",
  "pattern": "AMET",
  "case_sensitive": false
}
```


### Example 5
Calling `text_ends` with these arguments returns `true`.
#### json
```json
{
  "data": "\u00c4",
  "pattern": "\u00e4",
  "case_sensitive": false
}
```


### Example 6
Calling `text_ends` with these arguments returns `null`.
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
description: Text ends with another text
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

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_ends/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/texts/text_ends/schema.yaml)

## Sources

* [OpenEO Processes — text_ends](https://processes.openeo.org/#text_ends)
* [Open-EO/openeo-processes — text_ends.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/text_ends.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/texts/text_ends`

