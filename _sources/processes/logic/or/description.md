This Building Block proposes a schema representation of the OpenEO process [`or`](https://processes.openeo.org/#or) — *Logical OR*. It models the `arguments` object of a process graph node invoking `or`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **at least one** of the values is true. Evaluates parameter `x` before `y` and stops once the outcome is unambiguous. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false   | true
------- || ------- | ------- | ----
no-data || no-data | no-data | true
false   || no-data | false   | true
true    || true    | true    | true
```

## Source

OpenEO Processes specification: [`or`](https://processes.openeo.org/#or) ([openeo-processes/or.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/or.json)).
