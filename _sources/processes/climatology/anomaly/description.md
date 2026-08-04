This Building Block proposes a schema representation of the OpenEO process [`anomaly`](https://processes.openeo.org/#anomaly) — *Compute anomalies*. It models the `arguments` object of a process graph node invoking `anomaly`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes anomalies based on normals for temporal periods. It compares the data for each label in the temporal dimension with the corresponding data in the normals data cube by subtracting the normal from the data.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `normals` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension of type `temporal`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Source

OpenEO Processes specification: [`anomaly`](https://processes.openeo.org/#anomaly) ([openeo-processes/anomaly.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/anomaly.json)).
