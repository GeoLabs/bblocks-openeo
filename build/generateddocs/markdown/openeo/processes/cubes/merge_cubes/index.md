
# Merge cubes (Schema)

`ogc.openeo.processes.cubes.merge_cubes` *v0.1*

Merge two data cubes

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`merge_cubes`](https://processes.openeo.org/#merge_cubes) — *Merge two data cubes*. It models the `arguments` object of a process graph node invoking `merge_cubes`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

The process merges two 'compatible' data cubes.

The data cubes have to be compatible, which means that they must share a common subset of equal dimensions. To conveniently get to such a subset of equal dimensions, the process tries to align the horizontal spatial dimensions (axes `x` and `y`) implicitly with `resample_cube_spatial()` if required. `cube1` is the target data cube for resampling and the default parameters of `resample_cube_spatial()` apply. The equality for geometries follows the definition in the Simple Features standard by the OGC.

All dimensions share the same properties, such as name, type, reference system, and resolution. Dimensions can have disjoint or overlapping labels. If there is any overlap between the dimension labels, the parameter `overlap_resolver` must be specified to combine the two values for these overlapping labels. A merge operation without overlap should be reversible with (a set of) filter operations for each of the two cubes, if no implicit resampling was applied.

It is not possible to merge a vector and a raster data cube. Merging vector data cubes with different base geometry types (points, lines/line strings, polygons) is not possible and throws the `IncompatibleGeometryTypes` exception. The base geometry types can be merged with their corresponding multi geometry types.

After the merge, the dimensions with a natural/inherent label order (with a reference system this is each spatial and temporal dimensions) still have all dimension labels sorted. For other dimensions without inherent order, including bands, the dimension labels keep the order in which they are present in the original data cubes, and the dimension labels of `cube2` get appended to the dimension labels of `cube1`.

**Examples for merging two data cubes:**

1. Data cubes with the dimensions (`x`, `y`, `t`, `bands`) have the same dimension labels in `x`, `y` and `t`, but the labels for the dimension `bands` are `B1` and `B2` for the base data cube and `B3` and `B4` for the other. An overlap resolver is *not needed*. The merged data cube has the dimensions `x`, `y`, `t`, `bands`, and the dimension `bands` has four dimension labels: `B1`, `B2`, `B3`, `B4`.
2. Data cubes with the dimensions (`x`, `y`, `t`, `bands`) have the same dimension labels in `x`, `y` and `t`, but the labels for the dimension `bands` are `B1` and `B2` for the base data cube and `B2` and `B3` for the other. An overlap resolver is *required* to resolve overlap in band `B2`. The merged data cube has the dimensions `x`, `y`, `t` and `bands` and the dimension `bands` has three dimension labels: `B1`, `B2`, `B3`.
3. Data cubes with the dimensions (`x`, `y`, `t`) have the same dimension labels in `x`, `y` and `t`. There are two options:
   1. Keep the overlapping values separately in the merged data cube: An overlap resolver is *not needed*, but for each data cube you need to add a new dimension using `add_dimension()`. The new dimensions must be equal, except that the labels for the new dimensions must differ. The merged data cube has the same dimensions and labels as the original data cubes, plus the dimension added with `add_dimension()`, which has the two dimension labels after the merge.
   2. Combine the overlapping values into a single value: An overlap resolver is *required* to resolve the overlap for all values. The merged data cube has the same dimensions and labels as the original data cubes, but all values have been processed by the overlap resolver.
4. A data cube with dimensions (`x`, `y`, `t` / `bands`) or (`x`, `y`, `t`, `bands`) and another data cube with dimensions (`x`, `y`) have the same dimension labels in `x` and `y`. Merging them will join dimensions `x` and `y`, so the lower dimension cube is merged with each time step and band available in the higher dimensional cube. A use case for this is applying a digital elevation model to a spatio-temporal data cube. An overlap resolver is *required* to resolve the overlap for all pixels.

## Callback (child process) signature

The child process passed as `overlap_resolver` is called with the following named parameters:

- `x`: The overlapping value from the base data cube `cube1`.
- `y`: The overlapping value from the other data cube `cube2`.
- `context` (optional): Additional data passed by the user.

It must return: The value to be set in the merged data cube.

## Exceptions

- `OverlapResolverMissing`: Overlapping data cubes, but no overlap resolver has been specified.
- `IncompatibleGeometryTypes`: The geometry types are not compatible and can't be merged.

## Source

OpenEO Processes specification: [`merge_cubes`](https://processes.openeo.org/#merge_cubes) ([openeo-processes/merge_cubes.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/merge_cubes.json)).

## Examples

### Example 1
Calling `merge_cubes` with these arguments returns `{}`.

Data-cube-valued arguments/returns are shown as `from_parameter`/`from_node` references, as is standard practice in OpenEO process graphs (and as OpenEO's own official examples for other cube-manipulating processes do) — a data cube has no meaningful literal JSON form. This process has no official example in openeo-processes; this one is hand-built from its documented parameters. The return value is a data cube reference; it has no meaningful literal JSON form, so `{}` is shown as a placeholder satisfying only the `datacube` shared type's minimal object constraint.
#### json
```json
{
  "cube1": {
    "from_parameter": "cube1"
  },
  "cube2": {
    "from_parameter": "cube2"
  },
  "overlap_resolver": {
    "process_graph": {
      "add1": {
        "process_id": "add",
        "arguments": {
          "x": {
            "from_parameter": "x"
          },
          "y": {
            "from_parameter": "y"
          }
        },
        "result": true
      }
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Merge two data cubes
type: object
properties:
  cube1:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  cube2:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
  overlap_resolver:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/process-graph/schema.yaml
  context:
    description: Any data type.
required:
- cube1
- cube2

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/merge_cubes/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/merge_cubes/schema.yaml)

## Sources

* [OpenEO Processes — merge_cubes](https://processes.openeo.org/#merge_cubes)
* [Open-EO/openeo-processes — merge_cubes.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/merge_cubes.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/merge_cubes`

