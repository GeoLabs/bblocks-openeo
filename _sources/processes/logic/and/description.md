This Building Block proposes a schema representation of the OpenEO process [`and`](https://processes.openeo.org/#and) — *Logical AND*. It models the `arguments` object of a process graph node invoking `and`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **both** values are true.

Evaluates parameter `x` before `y` and stops once the outcome is unambiguous. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false | true
------- || ------- | ----- | -------
no-data || no-data | false | no-data
false   || false   | false | false
true    || no-data | false | true
```

## Source

OpenEO Processes specification: [`and`](https://processes.openeo.org/#and) ([openeo-processes/and.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/and.json)).
