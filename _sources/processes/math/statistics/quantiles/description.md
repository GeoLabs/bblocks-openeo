This Building Block proposes a schema representation of the OpenEO process [`quantiles`](https://processes.openeo.org/#quantiles) — *Quantiles*. It models the `arguments` object of a process graph node invoking `quantiles`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Calculates quantiles, which are cut points dividing the range of a sample distribution into either

1. intervals corresponding to the given probabilities *or*
2. equal-sized intervals (q-quantiles).

Either the parameter `probabilities` or `q` must be specified, otherwise the `QuantilesParameterMissing` exception is thrown. If both parameters are set the `QuantilesParameterConflict` exception is thrown.

Sample quantiles can be computed with several different algorithms. Hyndman and Fan (1996) have concluded on nine different types, which are commonly implemented in statistical software packages. This process is implementing type 7, which is implemented widely and often also the default type (e.g. in Excel, Julia, Python, R and S).

## Exceptions

- `QuantilesParameterMissing`: The process `quantiles` requires either the `probabilities` or `q` parameter to be set.
- `QuantilesParameterConflict`: The process `quantiles` only allows that either the `probabilities` or the `q` parameter is set.
- `AscendingProbabilitiesRequired`: The values passed for parameter `probabilities` must be sorted in ascending order.

## Source

OpenEO Processes specification: [`quantiles`](https://processes.openeo.org/#quantiles) ([openeo-processes/quantiles.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/quantiles.json)).
