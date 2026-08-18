
# Aggregate temporal period (Schema)

`ogc.openeo.processes.aggregate.aggregate_temporal_period` *v0.1*

Temporal aggregations based on calendar hierarchies

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`aggregate_temporal_period`](https://processes.openeo.org/#aggregate_temporal_period) — *Temporal aggregations based on calendar hierarchies*. It models the `arguments` object of a process graph node invoking `aggregate_temporal_period`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes a temporal aggregation based on calendar hierarchies such as years, months or seasons. For other calendar hierarchies `aggregate_temporal()` can be used.

For each interval, all data along the dimension will be passed through the reducer.

If the dimension is not set or is set to `null`, the data cube is expected to only have one temporal dimension.

## Callback (child process) signature

The child process passed as `reducer` is called with the following named parameters:

- `data`: A labeled array with elements of any type. If there's no data for the period, the array is empty.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the new data cube.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `TooManyDimensions`: The data cube contains multiple temporal dimensions. The parameter `dimension` must be specified.
- `DimensionNotAvailable`: A dimension with the specified name does not exist or no temporal dimension is available.

## Source

OpenEO Processes specification: [`aggregate_temporal_period`](https://processes.openeo.org/#aggregate_temporal_period) ([openeo-processes/aggregate_temporal_period.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_temporal_period.json)).

## Examples

### Monthly mean aggregation
Calling `aggregate_temporal_period` with these arguments returns `{}`.

`data` and the return value are data cube references — in an actual process graph these are node/parameter references (`from_node` / `from_parameter`), not literal JSON; `{}` here only satisfies the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {},
  "period": "month",
  "reducer": {
    "process_graph": {
      "mean1": {
        "process_id": "mean",
        "arguments": {
          "data": {
            "from_parameter": "data"
          }
        },
        "result": true
      }
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Temporal aggregations based on calendar hierarchies
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  period:
    type: string
    enum:
    - hour
    - day
    - week
    - dekad
    - month
    - season
    - tropical-season
    - year
    - decade
    - decade-ad
  reducer:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  dimension:
    type:
    - string
    - 'null'
  context:
    description: Any data type.
required:
- data
- period
- reducer

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/aggregate/aggregate_temporal_period/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/aggregate/aggregate_temporal_period/schema.yaml)

## Sources

* [OpenEO Processes — aggregate_temporal_period](https://processes.openeo.org/#aggregate_temporal_period)
* [Open-EO/openeo-processes — aggregate_temporal_period.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/aggregate_temporal_period.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/aggregate/aggregate_temporal_period`

