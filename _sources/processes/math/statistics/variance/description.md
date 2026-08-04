This Building Block proposes a schema representation of the OpenEO process [`variance`](https://processes.openeo.org/#variance) — *Variance*. It models the `arguments` object of a process graph node invoking `variance`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Computes the sample variance of an array of numbers by calculating the square of the standard deviation (see `sd()`). It is defined to be the expectation of the squared deviation of a random variable from its expected value. Basically, it measures how far the numbers in the array are spread out from their average value.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`variance`](https://processes.openeo.org/#variance) ([openeo-processes/variance.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/variance.json)).
