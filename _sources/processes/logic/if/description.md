This Building Block proposes a schema representation of the OpenEO process [`if`](https://processes.openeo.org/#if) — *If-Then-Else conditional*. It models the `arguments` object of a process graph node invoking `if`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

If the value passed is `true`, returns the value of the `accept` parameter, otherwise returns the value of the `reject` parameter.

This is basically an if-then-else construct as in other programming languages.

## Source

OpenEO Processes specification: [`if`](https://processes.openeo.org/#if) ([openeo-processes/if.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/if.json)).
