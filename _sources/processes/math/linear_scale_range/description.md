This Building Block proposes a schema representation of the OpenEO process [`linear_scale_range`](https://processes.openeo.org/#linear_scale_range) — *Linear transformation between two ranges*. It models the `arguments` object of a process graph node invoking `linear_scale_range`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Performs a linear transformation between the input and output range.

The given number in `x` is clipped to the bounds specified in `inputMin` and `inputMax` so that the underlying formula *`((x - inputMin) / (inputMax - inputMin)) * (outputMax - outputMin) + outputMin`* never returns a value outside of the range defined by `outputMin` and `outputMax`.

Potential use case include

* scaling values to the 8-bit range (0 - 255) often used for numeric representation of values in one of the channels of the [RGB colour model](https://en.wikipedia.org/wiki/RGB_color_model#Numeric_representations) or
* calculating percentages (0 - 100).

No-data values are passed through.

## Source

OpenEO Processes specification: [`linear_scale_range`](https://processes.openeo.org/#linear_scale_range) ([openeo-processes/linear_scale_range.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/linear_scale_range.json)).
