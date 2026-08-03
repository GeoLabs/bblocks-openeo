This Building Block proposes a schema representation of the OpenEO process [`array_create`](https://processes.openeo.org/#array_create) — *Create an array*. It models the `arguments` object of a process graph node invoking `array_create`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Creates a new array, which by default is empty.

The second parameter `repeat` allows to add the given array multiple times to the new array.

In most cases you can simply pass a (native) array to processes directly, but this process is especially useful to create a new array that is getting returned by a child process, for example in `apply_dimension()`.

## Source

OpenEO Processes specification: [`array_create`](https://processes.openeo.org/#array_create) ([openeo-processes/array_create.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_create.json)).
