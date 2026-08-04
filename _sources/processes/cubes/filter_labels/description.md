This Building Block proposes a schema representation of the OpenEO process [`filter_labels`](https://processes.openeo.org/#filter_labels) — *Filter dimension labels based on a condition*. It models the `arguments` object of a process graph node invoking `filter_labels`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the dimension labels in the data cube for the given dimension. Only the dimension labels that match the specified condition are preserved, all other labels with their corresponding data get removed.

## Callback (child process) signature

The child process passed as `condition` is called with the following named parameters:

- `value`: A single dimension label to compare against. The data type of the parameter depends on the dimension labels set for the dimension. Please note that for some dimension types a representation is used, e.g.

* dates and/or times are usually strings compliant to [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601),
* geometries can be a WKT string or an identifier.
- `context` (optional): Additional data passed by the user.

It must return: `true` if the dimension label should be kept in the data cube, otherwise `false`.

## Exceptions

- `DimensionNotAvailable`: A dimension with the specified name does not exist.

## Source

OpenEO Processes specification: [`filter_labels`](https://processes.openeo.org/#filter_labels) ([openeo-processes/filter_labels.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_labels.json)).
