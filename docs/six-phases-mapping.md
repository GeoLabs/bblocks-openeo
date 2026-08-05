# Mapping OpenEO Building Blocks onto the six-phase workflow framework

This document maps every Building Block in this registry onto GeoLabs' six-phase workflow profiling framework (D100 Activity 2, used for the W1/W2 workflow analysis): **filter configuration → selection/filtering → data retrieval → pre-processing → scientific computation → export/aggregation**.

**This is a proposed correspondence, produced after the registry was built and validated — it does not constrain the Building Blocks' own structure or granularity (see the [main plan](../README.md) for that). It is offered for review, not as a settled classification.**

A large group of Building Blocks — comparisons, logic, array utilities, temporal primitives, and a few structural types — don't belong to a single phase by nature: they're small, reusable processes typically invoked **inside** a callback (child process) of another Building Block, regardless of which phase that Building Block belongs to. These are listed under **Cross-cutting** rather than forced into one phase; see the note in that section.

Total Building Blocks mapped: 151 (33 shared types + 118 processes).


## 1. Filter configuration (9)

Building Blocks describing the *vocabulary* used to configure what to load: spatial/temporal/band/property selection criteria, expressed as parameters to `load_collection` or as filter arguments — before any data cube exists.

| Building Block | Identifier |
|---|---|
| OpenEO type: Band Name | `ogc.openeo.types.band-name` |
| OpenEO type: Bounding Box | `ogc.openeo.types.bounding-box` |
| OpenEO type: Collection ID | `ogc.openeo.types.collection-id` |
| OpenEO type: EPSG Code | `ogc.openeo.types.epsg-code` |
| OpenEO type: GeoJSON | `ogc.openeo.types.geojson` |
| OpenEO type: Filters | `ogc.openeo.types.metadata-filter` |
| OpenEO type: Single temporal interval | `ogc.openeo.types.temporal-interval` |
| OpenEO type: Multiple temporal intervals | `ogc.openeo.types.temporal-intervals` |
| OpenEO type: WKT2 definition | `ogc.openeo.types.wkt2-definition` |


## 2. Selection / filtering (12)

Processes that narrow down or mask an *already-referenced* data cube: dropping bands, labels, spatial/temporal extents, or pixels, based on a condition or extent.

| Building Block | Identifier |
|---|---|
| Array filter | `ogc.openeo.processes.arrays.array_filter` |
| Filter bands | `ogc.openeo.processes.cubes.filter_bands` |
| Filter bbox | `ogc.openeo.processes.cubes.filter_bbox` |
| Filter labels | `ogc.openeo.processes.cubes.filter_labels` |
| Filter spatial | `ogc.openeo.processes.cubes.filter_spatial` |
| Filter temporal | `ogc.openeo.processes.cubes.filter_temporal` |
| Mask | `ogc.openeo.processes.cubes.mask` |
| Mask polygon | `ogc.openeo.processes.cubes.mask_polygon` |
| Trim cube | `ogc.openeo.processes.cubes.trim_cube` |
| Text begins | `ogc.openeo.processes.texts.text_begins` |
| Text contains | `ogc.openeo.processes.texts.text_contains` |
| Text ends | `ogc.openeo.processes.texts.text_ends` |


## 3. Data retrieval (5)

Processes (and their supporting types) that bring data into a process graph as a data cube in the first place.

| Building Block | Identifier |
|---|---|
| Create data cube | `ogc.openeo.processes.cubes.create_data_cube` |
| Load collection | `ogc.openeo.processes.cubes.load_collection` |
| OpenEO type: Multiple File paths | `ogc.openeo.types.file-paths` |
| OpenEO type: Input File Format | `ogc.openeo.types.input-format` |
| OpenEO type: Options for Input File Formats | `ogc.openeo.types.input-format-options` |


## 4. Pre-processing (11)

Structural adjustments to a data cube — reprojection, resampling, dimension renaming/restructuring, merging — that prepare it for analysis without yet computing derived values.

| Building Block | Identifier |
|---|---|
| Add dimension | `ogc.openeo.processes.cubes.add_dimension` |
| Apply kernel | `ogc.openeo.processes.cubes.apply_kernel` |
| Dimension labels | `ogc.openeo.processes.cubes.dimension_labels` |
| Drop dimension | `ogc.openeo.processes.cubes.drop_dimension` |
| Merge cubes | `ogc.openeo.processes.cubes.merge_cubes` |
| Rename dimension | `ogc.openeo.processes.cubes.rename_dimension` |
| Rename labels | `ogc.openeo.processes.cubes.rename_labels` |
| Resample cube spatial | `ogc.openeo.processes.cubes.resample_cube_spatial` |
| Resample cube temporal | `ogc.openeo.processes.cubes.resample_cube_temporal` |
| Resample spatial | `ogc.openeo.processes.cubes.resample_spatial` |
| OpenEO type: Chunk Size | `ogc.openeo.types.chunk-size` |


## 5. Scientific computation (78)

The actual analytical/statistical processing: arithmetic, reducers, indices, trigonometric and statistical functions, and the `apply*`/`reduce_dimension` family that runs a computation over a cube's values.

| Building Block | Identifier |
|---|---|
| Aggregate temporal period | `ogc.openeo.processes.aggregate.aggregate_temporal_period` |
| Array append | `ogc.openeo.processes.arrays.array_append` |
| Array apply | `ogc.openeo.processes.arrays.array_apply` |
| Array concat | `ogc.openeo.processes.arrays.array_concat` |
| Array contains | `ogc.openeo.processes.arrays.array_contains` |
| Array create | `ogc.openeo.processes.arrays.array_create` |
| Array element | `ogc.openeo.processes.arrays.array_element` |
| Array find | `ogc.openeo.processes.arrays.array_find` |
| Array interpolate linear | `ogc.openeo.processes.arrays.array_interpolate_linear` |
| Array labels | `ogc.openeo.processes.arrays.array_labels` |
| Count | `ogc.openeo.processes.arrays.count` |
| First | `ogc.openeo.processes.arrays.first` |
| Last | `ogc.openeo.processes.arrays.last` |
| Order | `ogc.openeo.processes.arrays.order` |
| Rearrange | `ogc.openeo.processes.arrays.rearrange` |
| Sort | `ogc.openeo.processes.arrays.sort` |
| Anomaly | `ogc.openeo.processes.climatology.anomaly` |
| Aggregate spatial | `ogc.openeo.processes.cubes.aggregate_spatial` |
| Aggregate temporal | `ogc.openeo.processes.cubes.aggregate_temporal` |
| Apply | `ogc.openeo.processes.cubes.apply` |
| Apply dimension | `ogc.openeo.processes.cubes.apply_dimension` |
| Apply neighborhood | `ogc.openeo.processes.cubes.apply_neighborhood` |
| Apply polygon | `ogc.openeo.processes.cubes.apply_polygon` |
| Climatological normal | `ogc.openeo.processes.cubes.climatological_normal` |
| Ndvi | `ogc.openeo.processes.cubes.ndvi` |
| Reduce dimension | `ogc.openeo.processes.cubes.reduce_dimension` |
| Absolute | `ogc.openeo.processes.math.absolute` |
| Add | `ogc.openeo.processes.math.add` |
| Clip | `ogc.openeo.processes.math.clip` |
| Constant | `ogc.openeo.processes.math.constants.constant` |
| E | `ogc.openeo.processes.math.constants.e` |
| Pi | `ogc.openeo.processes.math.constants.pi` |
| Divide | `ogc.openeo.processes.math.divide` |
| Exp | `ogc.openeo.processes.math.exponential-and-logarithmic.exp` |
| Ln | `ogc.openeo.processes.math.exponential-and-logarithmic.ln` |
| Log | `ogc.openeo.processes.math.exponential-and-logarithmic.log` |
| Normalized difference | `ogc.openeo.processes.math.indices.normalized_difference` |
| Int | `ogc.openeo.processes.math.int` |
| Linear scale range | `ogc.openeo.processes.math.linear_scale_range` |
| Max | `ogc.openeo.processes.math.max` |
| Min | `ogc.openeo.processes.math.min` |
| Mod | `ogc.openeo.processes.math.mod` |
| Multiply | `ogc.openeo.processes.math.multiply` |
| Power | `ogc.openeo.processes.math.power` |
| Product | `ogc.openeo.processes.math.product` |
| Ceil | `ogc.openeo.processes.math.rounding.ceil` |
| Floor | `ogc.openeo.processes.math.rounding.floor` |
| Round | `ogc.openeo.processes.math.rounding.round` |
| Sgn | `ogc.openeo.processes.math.sgn` |
| Sqrt | `ogc.openeo.processes.math.sqrt` |
| Extrema | `ogc.openeo.processes.math.statistics.extrema` |
| Mean | `ogc.openeo.processes.math.statistics.mean` |
| Median | `ogc.openeo.processes.math.statistics.median` |
| Quantiles | `ogc.openeo.processes.math.statistics.quantiles` |
| Sd | `ogc.openeo.processes.math.statistics.sd` |
| Variance | `ogc.openeo.processes.math.statistics.variance` |
| Subtract | `ogc.openeo.processes.math.subtract` |
| Sum | `ogc.openeo.processes.math.sum` |
| Arccos | `ogc.openeo.processes.math.trigonometric.arccos` |
| Arcosh | `ogc.openeo.processes.math.trigonometric.arcosh` |
| Arcsin | `ogc.openeo.processes.math.trigonometric.arcsin` |
| Arctan | `ogc.openeo.processes.math.trigonometric.arctan` |
| Arctan2 | `ogc.openeo.processes.math.trigonometric.arctan2` |
| Arsinh | `ogc.openeo.processes.math.trigonometric.arsinh` |
| Artanh | `ogc.openeo.processes.math.trigonometric.artanh` |
| Cos | `ogc.openeo.processes.math.trigonometric.cos` |
| Cosh | `ogc.openeo.processes.math.trigonometric.cosh` |
| Sin | `ogc.openeo.processes.math.trigonometric.sin` |
| Sinh | `ogc.openeo.processes.math.trigonometric.sinh` |
| Tan | `ogc.openeo.processes.math.trigonometric.tan` |
| Tanh | `ogc.openeo.processes.math.trigonometric.tanh` |
| Text concat | `ogc.openeo.processes.texts.text_concat` |
| OpenEO type: Single File path | `ogc.openeo.types.file-path` |
| OpenEO type: Image Kernel | `ogc.openeo.types.kernel` |
| OpenEO type: UDF source code | `ogc.openeo.types.udf-code` |
| OpenEO type: UDF runtime | `ogc.openeo.types.udf-runtime` |
| OpenEO type: UDF Runtime version | `ogc.openeo.types.udf-runtime-version` |
| OpenEO type: URI | `ogc.openeo.types.uri` |


## 6. Export / aggregation (5)

Delivering or persisting the result of a workflow.

| Building Block | Identifier |
|---|---|
| Save result | `ogc.openeo.processes.cubes.save_result` |
| OpenEO type: Output File Format | `ogc.openeo.types.output-format` |
| OpenEO type: Options for Output File Formats | `ogc.openeo.types.output-format-options` |
| OpenEO type: STAC resource | `ogc.openeo.types.stac` |
| OpenEO type: Workspace ID | `ogc.openeo.types.workspace-id` |


## Cross-cutting (31)

Small, general-purpose processes and types (comparisons, logic, array utilities, temporal primitives, the process-graph/datacube types themselves, `run_udf`, ...) that are typically used **inside** a callback (child process) of a Building Block from another phase — e.g. `gt()` inside a `filter_labels` condition (phase 2) or inside a `reduce_dimension` reducer (phase 5). They are not tied to a single phase by nature; this table places them here rather than forcing an arbitrary choice.

| Building Block | Identifier |
|---|---|
| Between | `ogc.openeo.processes.comparison.between` |
| Date between | `ogc.openeo.processes.comparison.date_between` |
| GT | `ogc.openeo.processes.comparison.gt` |
| GTE | `ogc.openeo.processes.comparison.gte` |
| Is nan | `ogc.openeo.processes.comparison.is_nan` |
| Is nodata | `ogc.openeo.processes.comparison.is_nodata` |
| Is valid | `ogc.openeo.processes.comparison.is_valid` |
| LT | `ogc.openeo.processes.comparison.lt` |
| LTE | `ogc.openeo.processes.comparison.lte` |
| Run udf | `ogc.openeo.processes.cubes.run_udf` |
| Date shift | `ogc.openeo.processes.date-and-time.date_shift` |
| Inspect | `ogc.openeo.processes.development.inspect` |
| All | `ogc.openeo.processes.logic.all` |
| And | `ogc.openeo.processes.logic.and` |
| Any | `ogc.openeo.processes.logic.any` |
| If | `ogc.openeo.processes.logic.if` |
| Not | `ogc.openeo.processes.logic.not` |
| Or | `ogc.openeo.processes.logic.or` |
| Xor | `ogc.openeo.processes.logic.xor` |
| EQ | `ogc.openeo.processes.texts.eq` |
| NEQ | `ogc.openeo.processes.texts.neq` |
| OpenEO type: Data Cube | `ogc.openeo.types.datacube` |
| OpenEO type: Date only | `ogc.openeo.types.date` |
| OpenEO type: Date with Time | `ogc.openeo.types.date-time` |
| OpenEO type: Duration | `ogc.openeo.types.duration` |
| OpenEO type: Array with labels | `ogc.openeo.types.labeled-array` |
| OpenEO type: User-defined process | `ogc.openeo.types.process-graph` |
| OpenEO type: Raster data cube | `ogc.openeo.types.raster-cube` |
| OpenEO type: Time only | `ogc.openeo.types.time` |
| OpenEO type: Vector data cube | `ogc.openeo.types.vector-cube` |
| OpenEO type: Year only | `ogc.openeo.types.year` |

