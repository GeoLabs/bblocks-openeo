
# Climatological normal (Schema)

`ogc.openeo.processes.cubes.climatological_normal` *v0.1*

Compute climatology normals

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`climatological_normal`](https://processes.openeo.org/#climatological_normal) — *Compute climatology normals*. It models the `arguments` object of a process graph node invoking `climatological_normal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Climatological normal period is a usually 30 year average of a weather variable. Climatological normals are used as an average or baseline to evaluate climate events and provide context for yearly, monthly, daily or seasonal variability.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`climatological_normal`](https://processes.openeo.org/#climatological_normal) ([openeo-processes/climatological_normal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/climatological_normal.json)).

## Examples

### Example 1
Calling `climatological_normal` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "period": "month"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Compute climatology normals
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  period:
    type: string
    enum:
    - day
    - month
    - season
    - tropical-season
    - climatology-period
  climatology_period:
    type: array
    uniqueItems: true
    minItems: 2
    maxItems: 2
    items:
      $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/year/schema.yaml
required:
- data
- period

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/climatological_normal/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/climatological_normal/schema.yaml)

## Sources

* [OpenEO Processes — climatological_normal](https://processes.openeo.org/#climatological_normal)
* [Open-EO/openeo-processes — climatological_normal.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/climatological_normal.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/climatological_normal`

