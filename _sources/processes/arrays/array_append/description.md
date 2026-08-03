This Building Block proposes a schema representation of the OpenEO process [`array_append`](https://processes.openeo.org/#array_append) — *Append a value to an array*. It models the `arguments` object of a process graph node invoking `array_append`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Appends a new value to the end of the array, which may also include a new label for labeled arrays.

## Exceptions

- `LabelExists`: An array element with the specified label already exists.
- `ArrayNotLabeled`: A label can't be provided as the given array is not labeled.

## Source

OpenEO Processes specification: [`array_append`](https://processes.openeo.org/#array_append) ([openeo-processes/array_append.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_append.json)).
