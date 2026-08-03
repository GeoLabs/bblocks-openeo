This Building Block proposes a schema representation of the OpenEO process [`array_concat`](https://processes.openeo.org/#array_concat) — *Merge two arrays*. It models the `arguments` object of a process graph node invoking `array_concat`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Concatenates two arrays into a single array by appending the second array to the first array.

Array labels are kept only if both given arrays are labeled. Otherwise, the labels get discarded from both arrays. The process fails with an `ArrayLabelConflict` exception if a label is present in both arrays. Conflicts must be resolved beforehand.

## Exceptions

- `ArrayLabelConflict`: At least one label exists in both arrays and the conflict must be resolved before.

## Source

OpenEO Processes specification: [`array_concat`](https://processes.openeo.org/#array_concat) ([openeo-processes/array_concat.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_concat.json)).
