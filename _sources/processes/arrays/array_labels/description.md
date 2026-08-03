This Building Block proposes a schema representation of the OpenEO process [`array_labels`](https://processes.openeo.org/#array_labels) — *Get the labels for an array*. It models the `arguments` object of a process graph node invoking `array_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives all labels for a labeled array or gives all indices for an array without labels. If the array is not labeled, an array with the zero-based indices is returned. The labels or indices have the same order as in the array.

## Source

OpenEO Processes specification: [`array_labels`](https://processes.openeo.org/#array_labels) ([openeo-processes/array_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_labels.json)).
