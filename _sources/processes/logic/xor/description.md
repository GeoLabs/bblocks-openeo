This Building Block proposes a schema representation of the OpenEO process [`xor`](https://processes.openeo.org/#xor) — *Logical XOR (exclusive or)*. It models the `arguments` object of a process graph node invoking `xor`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Checks if **exactly one** of the values is true. If any argument is a no-data value, the result will be the no-data value whenever the outcome is ambiguous.

**Truth table:**

```
x \ y   || no-data | false   | true
------- || ------- | ------- | -------
no-data || no-data | no-data | no-data
false   || no-data | false   | true
true    || no-data | true    | false
```

## Source

OpenEO Processes specification: [`xor`](https://processes.openeo.org/#xor) ([openeo-processes/xor.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/xor.json)).
