
# Date between (Schema)

`ogc.openeo.processes.comparison.date_between` *v0.1*

Between comparison for dates and times

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`date_between`](https://processes.openeo.org/#date_between) — *Between comparison for dates and times*. It models the `arguments` object of a process graph node invoking `date_between`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

By default, this process checks whether `x` is later than or equal to `min` and before or equal to `max`.

If `exclude_max` is set to `true` the upper bound is excluded so that the process checks whether `x` is later than or equal to `min` and before `max`.

Lower and upper bounds are not allowed to be swapped. So `min` MUST be before or equal to `max` or otherwise the process always returns `false`.

## Source

OpenEO Processes specification: [`date_between`](https://processes.openeo.org/#date_between) ([openeo-processes/date_between.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_between.json)).

## Examples

### Example 1
Calling `date_between` with these arguments returns `false`.
#### json
```json
{
  "x": "2020-01-01",
  "min": "2021-01-01",
  "max": "2022-01-01"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Between comparison for dates and times
type: object
properties:
  x:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.yaml
  min:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.yaml
  max:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/time/schema.yaml
  exclude_max:
    type: boolean
required:
- x
- min
- max

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/date_between/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/comparison/date_between/schema.yaml)

## Sources

* [OpenEO Processes — date_between](https://processes.openeo.org/#date_between)
* [Open-EO/openeo-processes — date_between.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_between.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/comparison/date_between`

