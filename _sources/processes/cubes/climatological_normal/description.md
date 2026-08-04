This Building Block proposes a schema representation of the OpenEO process [`climatological_normal`](https://processes.openeo.org/#climatological_normal) — *Compute climatology normals*. It models the `arguments` object of a process graph node invoking `climatological_normal`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Climatological normal period is a usually 30 year average of a weather variable. Climatological normals are used as an average or baseline to evaluate climate events and provide context for yearly, monthly, daily or seasonal variability.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`climatological_normal`](https://processes.openeo.org/#climatological_normal) ([openeo-processes/climatological_normal.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/climatological_normal.json)).
