This Building Block proposes a schema representation of the OpenEO process [`array_element`](https://processes.openeo.org/#array_element) — *Get an element from an array*. It models the `arguments` object of a process graph node invoking `array_element`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Gives the element with the specified index or label from the array.

Either the parameter `index` or `label` must be specified, otherwise the `ArrayElementParameterMissing` exception is thrown. If both parameters are set the `ArrayElementParameterConflict` exception is thrown.

## Exceptions

- `ArrayElementNotAvailable`: The array has no element with the specified index or label.
- `ArrayElementParameterMissing`: The process `array_element` requires either the `index` or `labels` parameter to be set.
- `ArrayElementParameterConflict`: The process `array_element` only allows that either the `index` or the `labels` parameter is set.
- `ArrayNotLabeled`: The array is not a labeled array, but the `label` parameter is set. Use the `index` instead.

## Source

OpenEO Processes specification: [`array_element`](https://processes.openeo.org/#array_element) ([openeo-processes/array_element.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/array_element.json)).
