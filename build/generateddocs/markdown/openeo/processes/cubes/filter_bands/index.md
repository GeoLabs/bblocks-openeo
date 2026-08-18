
# Filter bands (Schema)

`ogc.openeo.processes.cubes.filter_bands` *v0.1*

Filter the bands by names

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`filter_bands`](https://processes.openeo.org/#filter_bands) — *Filter the bands by names*. It models the `arguments` object of a process graph node invoking `filter_bands`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Filters the bands in the data cube so that bands that don't match any of the criteria are dropped from the data cube. The data cube is expected to have only one dimension of type `bands`. Fails with a `DimensionMissing` exception if no such dimension exists.

The following criteria can be used to select bands:

* `bands`: band name or common band name (e.g. `B01`, `B8A`, `red` or `nir`)
* `wavelengths`: ranges of wavelengths in micrometers (μm) (e.g. 0.5 - 0.6)

All these information are exposed in the band metadata of the collection. To keep algorithms interoperable it is recommended to prefer the common band names or the wavelengths over band names that are specific to the collection and/or back-end.

If multiple criteria are specified, any of them must match and not all of them, i.e. they are combined with an OR-operation. If no criteria are specified, the `BandFilterParameterMissing` exception must be thrown.

**Important:** The order of the specified array defines the order of the bands in the data cube, which can be important for subsequent processes. If multiple bands are matched by a single criterion (e.g. a range of wavelengths), they stay in the original order.

## Data cube dimension requirements

- `data` (a `datacube`): must include a dimension matching `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).
- `(return value)` (a `datacube`): must include a dimension matching `bands`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `BandFilterParameterMissing`: The process `filter_bands` requires any of the parameters `bands`, `common_names` or `wavelengths` to be set.
- `DimensionMissing`: A band dimension is missing.

## Source

OpenEO Processes specification: [`filter_bands`](https://processes.openeo.org/#filter_bands) ([openeo-processes/filter_bands.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_bands.json)).

## Examples

### Example 1
Calling `filter_bands` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "data": {
    "from_parameter": "data"
  },
  "bands": [
    "B04",
    "B08"
  ]
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Filter the bands by names
type: object
properties:
  data:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  bands:
    type: array
    items:
      $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.yaml
  wavelengths:
    type: array
    items:
      type: array
      minItems: 2
      maxItems: 2
      items:
        type: number
      examples:
      - - - 0.45
          - 0.5
        - - 0.6
          - 0.7
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_bands/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/filter_bands/schema.yaml)

## Sources

* [OpenEO Processes — filter_bands](https://processes.openeo.org/#filter_bands)
* [Open-EO/openeo-processes — filter_bands.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/filter_bands.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/filter_bands`

