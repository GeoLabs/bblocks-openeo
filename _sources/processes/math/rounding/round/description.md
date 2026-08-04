This Building Block proposes a schema representation of the OpenEO process [`round`](https://processes.openeo.org/#round) — *Round to a specified precision*. It models the `arguments` object of a process graph node invoking `round`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Rounds a real number `x` to specified precision `p`.

If `x` is halfway between closest numbers of precision `p`, it is rounded to the closest even number of precision `p`.
This behavior follows [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) and is often called "round to nearest (even)" or "banker's rounding". It minimizes rounding errors that result from consistently rounding a midpoint value in a single direction.

No-data values are passed through.

## Source

OpenEO Processes specification: [`round`](https://processes.openeo.org/#round) ([openeo-processes/round.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/round.json)).
