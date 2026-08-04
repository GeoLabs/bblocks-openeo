This Building Block proposes a schema representation of the OpenEO process [`all`](https://processes.openeo.org/#all) — *Are all of the values true?*. It models the `arguments` object of a process graph node invoking `all`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **all** of the values in `data` are true. If no value is given (i.e. the array is empty) the process returns `true`.

By default, all no-data values are ignored so that the process returns `true` if all values are no-data or true, and `false` otherwise. Setting the `ignore_nodata` flag to `false` takes no-data values into account and the array values are reduced pairwise according to the following truth table:

```
        || no-data | false | true
------- || ------- | ----- | -------
no-data || no-data | false | no-data
false   || false   | false | false
true    || no-data | false | true
```

**Remark:** The process evaluates all values in an arbitrary order and stops once the outcome is unambiguous, i.e. when either a `false` value is encountered, or when all values have been taken into account.

## Source

OpenEO Processes specification: [`all`](https://processes.openeo.org/#all) ([openeo-processes/all.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/all.json)).
