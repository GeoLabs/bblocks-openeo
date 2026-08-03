This Building Block proposes a schema representation of the OpenEO process [`array_interpolate_linear`](https://processes.openeo.org/#array_interpolate_linear) — *One-dimensional linear interpolation for arrays*. It models the `arguments` object of a process graph node invoking `array_interpolate_linear`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Performs a linear interpolation for each of the NaN and no-data values in the array given, except for leading and trailing NaN and no-data values.

The linear interpolants are defined by the array indices or labels (x axis) and the values in the array (y axis).

## Source

OpenEO Processes specification: [`array_interpolate_linear`](https://processes.openeo.org/#array_interpolate_linear) ([openeo-processes/array_interpolate_linear.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_interpolate_linear.json)).
