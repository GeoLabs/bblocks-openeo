This Building Block proposes a schema representation of the OpenEO process [`clip`](https://processes.openeo.org/#clip) — *Clip a value between a minimum and a maximum*. It models the `arguments` object of a process graph node invoking `clip`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Clips a number between specified minimum and maximum values. A value larger than the maximum value is set to the maximum value, a value lower than the minimum value is set to the minimum value. If the maximum value is smaller than the minimum number, the process throws a `MinMaxSwapped` exception.

No-data values are passed through.

## Exceptions

- `MinMaxSwapped`: The minimum value should be lower than or equal to the maximum value.

## Source

OpenEO Processes specification: [`clip`](https://processes.openeo.org/#clip) ([openeo-processes/clip.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/clip.json)).
