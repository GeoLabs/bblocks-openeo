
# Resample cube temporal (Schema)

`ogc.openeo.processes.cubes.resample_cube_temporal` *v0.1*

Resample temporal dimensions to match a target data cube

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`resample_cube_temporal`](https://processes.openeo.org/#resample_cube_temporal) — *Resample temporal dimensions to match a target data cube*. It models the `arguments` object of a process graph node invoking `resample_cube_temporal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Resamples one or more given temporal dimensions from a source data cube to align with the corresponding dimensions of the given target data cube using the nearest neighbor method. Returns a new data cube with the resampled dimensions.

By default, this process simply takes the nearest neighbor independent of the value (including no-data values). Depending on the data cubes this may lead to values being assigned to two target timestamps. To only consider valid values in a specific range around the target timestamps, use the parameter `valid_within`.

The rare case of ties is resolved by choosing the earlier timestamps.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `target` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `DimensionMismatch`: The temporal dimensions for resampling don't match.
- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`resample_cube_temporal`](https://processes.openeo.org/#resample_cube_temporal) ([openeo-processes/resample_cube_temporal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_cube_temporal.json)).

## Examples

### Example 1
Calling `resample_cube_temporal` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "target": {
    "from_parameter": "target"
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Resample temporal dimensions to match a target data cube
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  target:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  dimension:
    type:
    - string
    - 'null'
  valid_within:
    type:
    - number
    - 'null'
required:
- data
- target

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/resample_cube_temporal/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/resample_cube_temporal/schema.yaml)

## Sources

* [OpenEO Processes — resample_cube_temporal](https://processes.openeo.org/#resample_cube_temporal)
* [Open-EO/openeo-processes — resample_cube_temporal.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/resample_cube_temporal.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/resample_cube_temporal`

