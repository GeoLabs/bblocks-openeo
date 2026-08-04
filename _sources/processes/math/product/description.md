This Building Block proposes a schema representation of the OpenEO process [`product`](https://processes.openeo.org/#product) — *Compute the product by multiplying numbers*. It models the `arguments` object of a process graph node invoking `product`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Multiplies all elements in a sequential array of numbers and returns the computed product.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`product`](https://processes.openeo.org/#product) ([openeo-processes/product.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/product.json)).
