
# Anomaly (Schema)

`ogc.openeo.processes.climatology.anomaly` *v0.1*

Compute anomalies

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`anomaly`](https://processes.openeo.org/#anomaly) — *Compute anomalies*. It models the `arguments` object of a process graph node invoking `anomaly`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes anomalies based on normals for temporal periods. It compares the data for each label in the temporal dimension with the corresponding data in the normals data cube by subtracting the normal from the data.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `normals` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`anomaly`](https://processes.openeo.org/#anomaly) ([openeo-processes/anomaly.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/anomaly.json)).

## Examples

### Anomaly against monthly normals
Calling `anomaly` with these arguments returns `{}`.

`data`, `normals` and the return value are data cube references — in an actual process graph these are node/parameter references, not literal JSON; `{}` here only satisfies the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {},
  "normals": {},
  "period": "month"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Compute anomalies
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  normals:
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
    - climatology-period
    - single-period
required:
- data
- normals
- period

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/climatology/anomaly/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/climatology/anomaly/schema.yaml)

## Sources

* [OpenEO Processes — anomaly](https://processes.openeo.org/#anomaly)
* [Open-EO/openeo-processes — anomaly.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/anomaly.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/climatology/anomaly`

