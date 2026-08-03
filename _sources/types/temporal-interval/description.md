This Building Block proposes a schema representation of the OpenEO shared subtype `temporal-interval`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

Left-closed temporal interval, represented as two-element array with the following elements:

1. The first element is the start of the temporal interval. The specified time instant is **included** in the interval.
2. The second element is the end of the temporal interval. The specified time instant is **excluded** from the interval.

The second element must always be greater/later than the first element. Otherwise, an exception is thrown.

The specified temporal strings follow [RFC 3339](https://www.rfc-editor.org/rfc/rfc3339.html). Also supports unbounded intervals by setting one of the boundaries to `null`, but never both.
