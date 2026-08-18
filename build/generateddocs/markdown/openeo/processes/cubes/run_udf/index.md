
# Run udf (Schema)

`ogc.openeo.processes.cubes.run_udf` *v0.1*

Run a UDF

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`run_udf`](https://processes.openeo.org/#run_udf) — *Run a UDF*. It models the `arguments` object of a process graph node invoking `run_udf`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Runs a UDF in one of the supported runtime environments.

The process can either:

1. load and run a UDF stored in a file on the server-side workspace of the authenticated user. The path to the UDF file must be relative to the root directory of the user's workspace.
2. fetch and run a remotely stored and published UDF by absolute URI.
3. run the source code specified inline as string.

The loaded UDF can be executed in several processes such as `aggregate_spatial()`, `apply()`, `apply_dimension()` and `reduce_dimension()`. The user must ensure that the data is provided in a way that the UDF code can make sense of it.

## Exceptions

- `InvalidRuntime`: The specified UDF runtime is not supported.
- `InvalidVersion`: The specified UDF runtime version is not supported.
- `FileNotFound`: The specified file does not exist.

## Source

OpenEO Processes specification: [`run_udf`](https://processes.openeo.org/#run_udf) ([openeo-processes/run_udf.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/run_udf.json)).

## Examples

### Example 1
Calling `run_udf` with these arguments returns `0.42`.

The return value's actual type depends entirely on what the UDF code returns (`data` is of type "any"); the illustrative value shown here is not computed.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "udf": "import numpy as np\n\ndef apply(data):\n    return data * 2\n",
  "runtime": "Python"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Run a UDF
type: object
properties:
  data:
    description: A value of any data type.
  udf:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/uri/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/file-path/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-code/schema.yaml
  runtime:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-runtime/schema.yaml
  version:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/udf-runtime-version/schema.yaml
    - title: Default runtime version
      type: 'null'
  context:
    description: Any data type.
required:
- data
- udf
- runtime

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/run_udf/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/run_udf/schema.yaml)

## Sources

* [OpenEO Processes — run_udf](https://processes.openeo.org/#run_udf)
* [Open-EO/openeo-processes — run_udf.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/run_udf.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/run_udf`

