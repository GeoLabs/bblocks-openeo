This Building Block proposes a schema representation of the OpenEO process [`any`](https://processes.openeo.org/#any) — *Is at least one value true?*. It models the `arguments` object of a process graph node invoking `any`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **any** (i.e. at least one) value in `data` is `true`. If no value is given (i.e. the array is empty) the process returns `false`.

By default all no-data values are ignored so that the process returns `true` if at least one value is true and `false` otherwise. Setting the `ignore_nodata` flag to `false` takes no-data values into account and the array values are reduced pairwise according to the following truth table:

```
        || no-data | false   | true
------- || ------- | ------- | ----
no-data || no-data | no-data | true
false   || no-data | false   | true
true    || true    | true    | true
```

**Remark:** The process evaluates all values in an arbitrary order and stops once the outcome is unambiguous, i.e. when either a `true` value is encountered, or when all values have been taken into account.

## Source

OpenEO Processes specification: [`any`](https://processes.openeo.org/#any) ([openeo-processes/any.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/any.json)).
