This Building Block proposes a schema representation of the OpenEO process [`rename_labels`](https://processes.openeo.org/#rename_labels) — *Rename dimension labels*. It models the `arguments` object of a process graph node invoking `rename_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Renames the labels of the specified dimension in the data cube from `source` to `target`.

If the array for the source labels is empty (the default), the dimension labels are enumerated with zero-based numbering (0,1,2,3,...) so that the dimension labels directly map to the indices of the array specified for the parameter `target`. Otherwise, the number of the source and target labels must be equal. If none of these requirements is fulfilled, the `LabelMismatch` exception is thrown.

This process doesn't change the order of the labels and their corresponding data.

## Exceptions

- `LabelsNotEnumerated`: The dimension labels are not enumerated.
- `LabelMismatch`: The number of labels in the parameters `source` and `target` don't match.
- `LabelNotAvailable`: A label with the specified name does not exist.
- `LabelExists`: A label with the specified name exists.

## Source

OpenEO Processes specification: [`rename_labels`](https://processes.openeo.org/#rename_labels) ([openeo-processes/rename_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/rename_labels.json)).
