
# OpenEO type: User-defined process (Schema)

`ogc.openeo.types.process-graph` *v0.1*

A user-defined process (child process graph) passed as a callback argument.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `process-graph`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

An process graph that is passed as an argument and is expected to be executed by the process. Parameters passed to the process graph are specified in the `parameters` property of the corresponding schema.

## Examples

### Example value
A minimal callback process graph that computes `1 + 1`.
#### json
```json
{
  "process_graph": {
    "add1": {
      "process_id": "add",
      "arguments": {
        "x": 1,
        "y": 1
      },
      "result": true
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
subtype: process-graph
title: User-defined process
description: An process graph that is passed as an argument and is expected to be
  executed by the process. Parameters passed to the process graph are specified in
  the `parameters` property of the corresponding schema.
required:
- process_graph
properties:
  process_graph:
    type: object
    additionalProperties:
      type: object
      required:
      - process_id
      - arguments
      properties:
        process_id:
          type: string
        arguments: {}

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/process-graph`

