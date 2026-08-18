
# Filter temporal (Schema)

`ogc.openeo.processes.cubes.filter_temporal` *v0.1*

Temporal filter based on temporal intervals

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`filter_temporal`](https://processes.openeo.org/#filter_temporal) — *Temporal filter based on temporal intervals*. It models the `arguments` object of a process graph node invoking `filter_temporal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Limits the data cube to the specified interval of dates and/or times.

More precisely, the filter checks whether each of the temporal dimension labels is greater than or equal to the lower boundary (start date/time) and less than the value of the upper boundary (end date/time). This corresponds to a left-closed interval, which contains the lower boundary but not the upper boundary.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.
- `TemporalExtentEmpty`: The temporal extent is empty. The second instant in time must always be greater/later than the first instant in time.

## Source

OpenEO Processes specification: [`filter_temporal`](https://processes.openeo.org/#filter_temporal) ([openeo-processes/filter_temporal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_temporal.json)).

## Examples

### Example 1
Calling `filter_temporal` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "extent": [
    "2018-01-01",
    "2019-01-01"
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Temporal filter based on temporal intervals
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  extent:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-interval/schema.yaml
  dimension:
    type:
    - string
    - 'null'
required:
- data
- extent

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_temporal/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_temporal/schema.yaml)

## Sources

* [OpenEO Processes — filter_temporal](https://processes.openeo.org/#filter_temporal)
* [Open-EO/openeo-processes — filter_temporal.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_temporal.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/filter_temporal`

