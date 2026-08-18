# OpenEO Building Blocks

An investigation into representing the [OpenEO](https://openeo.org) process catalogue —
an OGC Community Standard — as OGC Building Blocks. Each Building Block here is a proposed
schema correspondence for one OpenEO process or shared subtype, not a settled equivalence.


This register is produced under OSPD 2026 D100 Activity 4 (GeoLabs). It models the stable
processes of the [OpenEO Processes specification](https://processes.openeo.org/) — sourced from
[Open-EO/openeo-processes](https://github.com/Open-EO/openeo-processes) — as OGC Building Block
schemas, grouped by OpenEO's own process categories. Shared OpenEO subtypes (data cubes, process
graphs, temporal intervals, etc.) are modelled once under `types/` and reused by reference across
process Building Blocks.

This is an open investigation: each mapping between an OpenEO process and an OGC Building Block
is a proposed correspondence, offered for review, not a final or authoritative statement.


## Building Blocks

### `ogc.openeo.types.process-graph` — OpenEO type: User-defined process

**Type:** schema

A user-defined process (child process graph) passed as a callback argument.

### `ogc.openeo.types.datacube` — OpenEO type: Data Cube

**Type:** schema

A data cube with an arbitrary number of dimensions, without a required dimension typing.

### `ogc.openeo.processes.arrays.array_append` — Array append

**Type:** schema

Append a value to an array

### `ogc.openeo.processes.arrays.array_concat` — Array concat

**Type:** schema

Merge two arrays

### `ogc.openeo.processes.arrays.array_contains` — Array contains

**Type:** schema

Check whether the array contains a given value

### `ogc.openeo.processes.arrays.array_create` — Array create

**Type:** schema

Create an array

### `ogc.openeo.processes.arrays.array_element` — Array element

**Type:** schema

Get an element from an array

### `ogc.openeo.processes.arrays.array_find` — Array find

**Type:** schema

Get the index for a value in an array

### `ogc.openeo.processes.arrays.array_interpolate_linear` — Array interpolate linear

**Type:** schema

One-dimensional linear interpolation for arrays

### `ogc.openeo.processes.arrays.array_labels` — Array labels

**Type:** schema

Get the labels for an array

### `ogc.openeo.processes.arrays.first` — First

**Type:** schema

First element

### `ogc.openeo.processes.arrays.last` — Last

**Type:** schema

Last element

### `ogc.openeo.types.date-time` — OpenEO type: Date with Time

**Type:** schema

A calendar date and time (RFC 3339 date-time).

### `ogc.openeo.types.date` — OpenEO type: Date only

**Type:** schema

A calendar date without a time component (RFC 3339 full-date, UTC).

### `ogc.openeo.processes.arrays.rearrange` — Rearrange

**Type:** schema

Sort an array based on a permutation

### `ogc.openeo.processes.comparison.between` — Between

**Type:** schema

Between comparison

### `ogc.openeo.types.time` — OpenEO type: Time only

**Type:** schema

A time of day without a date component (UTC).

### `ogc.openeo.processes.comparison.gt` — GT

**Type:** schema

Greater than comparison

### `ogc.openeo.processes.comparison.gte` — GTE

**Type:** schema

Greater than or equal to comparison

### `ogc.openeo.processes.comparison.is_nan` — Is nan

**Type:** schema

Value is not a number

### `ogc.openeo.processes.comparison.is_nodata` — Is nodata

**Type:** schema

Value is a no-data value

### `ogc.openeo.processes.comparison.is_valid` — Is valid

**Type:** schema

Value is valid data

### `ogc.openeo.processes.comparison.lt` — LT

**Type:** schema

Less than comparison

### `ogc.openeo.processes.comparison.lte` — LTE

**Type:** schema

Less than or equal to comparison

### `ogc.openeo.types.geojson` — OpenEO type: GeoJSON

**Type:** schema

A GeoJSON geometry, feature or feature collection (deprecated in favour of `datacube`/`vector-cube` handling).

### `ogc.openeo.types.kernel` — OpenEO type: Image Kernel

**Type:** schema

A two-dimensional numeric array used as a convolution kernel.

### `ogc.openeo.types.year` — OpenEO type: Year only

**Type:** schema

A calendar year given as an integer.

### `ogc.openeo.processes.cubes.create_data_cube` — Create data cube

**Type:** schema

Create an empty data cube

### `ogc.openeo.types.band-name` — OpenEO type: Band Name

**Type:** schema

A band name or common band name identifying a band in a data cube.

### `ogc.openeo.types.collection-id` — OpenEO type: Collection ID

**Type:** schema

An identifier for a collection offered by an OpenEO back-end.

### `ogc.openeo.types.epsg-code` — OpenEO type: EPSG Code

**Type:** schema

A coordinate reference system identified by its EPSG code.

### `ogc.openeo.types.wkt2-definition` — OpenEO type: WKT2 definition

**Type:** schema

A coordinate reference system given as a WKT2 string.

### `ogc.openeo.types.udf-runtime-version` — OpenEO type: UDF Runtime version

**Type:** schema

The version identifier of a UDF runtime.

### `ogc.openeo.types.uri` — OpenEO type: URI

**Type:** schema

A URI as defined by RFC 3986.

### `ogc.openeo.types.file-path` — OpenEO type: Single File path

**Type:** schema

A relative path to a single user-uploaded file.

### `ogc.openeo.types.udf-code` — OpenEO type: UDF source code

**Type:** schema

The multi-line source code of a user-defined function (UDF).

### `ogc.openeo.types.udf-runtime` — OpenEO type: UDF runtime

**Type:** schema

The identifier of a UDF runtime.

### `ogc.openeo.types.output-format-options` — OpenEO type: Options for Output File Formats

**Type:** schema

Key-value pairs of options for a given output file format.

### `ogc.openeo.types.output-format` — OpenEO type: Output File Format

**Type:** schema

The identifier of a file format supported by the back-end for exporting data.

### `ogc.openeo.processes.development.inspect` — Inspect

**Type:** schema

Add information to the logs

### `ogc.openeo.processes.logic.all` — All

**Type:** schema

Are all of the values true?

### `ogc.openeo.processes.logic.and` — And

**Type:** schema

Logical AND

### `ogc.openeo.processes.logic.any` — Any

**Type:** schema

Is at least one value true?

### `ogc.openeo.processes.logic.if` — If

**Type:** schema

If-Then-Else conditional

### `ogc.openeo.processes.logic.not` — Not

**Type:** schema

Inverting a boolean

### `ogc.openeo.processes.logic.or` — Or

**Type:** schema

Logical OR

### `ogc.openeo.processes.logic.xor` — Xor

**Type:** schema

Logical XOR (exclusive or)

### `ogc.openeo.processes.math.absolute` — Absolute

**Type:** schema

Absolute value

### `ogc.openeo.processes.math.add` — Add

**Type:** schema

Addition of two numbers

### `ogc.openeo.processes.math.clip` — Clip

**Type:** schema

Clip a value between a minimum and a maximum

### `ogc.openeo.processes.math.constants.constant` — Constant

**Type:** schema

Define a constant value

### `ogc.openeo.processes.math.constants.e` — E

**Type:** schema

Euler's number (e)

### `ogc.openeo.processes.math.constants.pi` — Pi

**Type:** schema

Pi (π)

### `ogc.openeo.processes.math.divide` — Divide

**Type:** schema

Division of two numbers

### `ogc.openeo.processes.math.exponential-and-logarithmic.exp` — Exp

**Type:** schema

Exponentiation to the base e

### `ogc.openeo.processes.math.exponential-and-logarithmic.ln` — Ln

**Type:** schema

Natural logarithm

### `ogc.openeo.processes.math.exponential-and-logarithmic.log` — Log

**Type:** schema

Logarithm to a base

### `ogc.openeo.processes.math.indices.normalized_difference` — Normalized difference

**Type:** schema

Normalized difference

### `ogc.openeo.processes.math.int` — Int

**Type:** schema

Integer part of a number

### `ogc.openeo.processes.math.linear_scale_range` — Linear scale range

**Type:** schema

Linear transformation between two ranges

### `ogc.openeo.processes.math.max` — Max

**Type:** schema

Maximum value

### `ogc.openeo.processes.math.min` — Min

**Type:** schema

Minimum value

### `ogc.openeo.processes.math.mod` — Mod

**Type:** schema

Modulo

### `ogc.openeo.processes.math.multiply` — Multiply

**Type:** schema

Multiplication of two numbers

### `ogc.openeo.processes.math.power` — Power

**Type:** schema

Exponentiation

### `ogc.openeo.processes.math.product` — Product

**Type:** schema

Compute the product by multiplying numbers

### `ogc.openeo.processes.math.rounding.ceil` — Ceil

**Type:** schema

Round fractions up

### `ogc.openeo.processes.math.rounding.floor` — Floor

**Type:** schema

Round fractions down

### `ogc.openeo.processes.math.rounding.round` — Round

**Type:** schema

Round to a specified precision

### `ogc.openeo.processes.math.sgn` — Sgn

**Type:** schema

Signum

### `ogc.openeo.processes.math.sqrt` — Sqrt

**Type:** schema

Square root

### `ogc.openeo.processes.math.statistics.extrema` — Extrema

**Type:** schema

Minimum and maximum values

### `ogc.openeo.processes.math.statistics.mean` — Mean

**Type:** schema

Arithmetic mean (average)

### `ogc.openeo.processes.math.statistics.median` — Median

**Type:** schema

Statistical median

### `ogc.openeo.processes.math.statistics.quantiles` — Quantiles

**Type:** schema

Quantiles

### `ogc.openeo.processes.math.statistics.sd` — Sd

**Type:** schema

Standard deviation

### `ogc.openeo.processes.math.statistics.variance` — Variance

**Type:** schema

Variance

### `ogc.openeo.processes.math.subtract` — Subtract

**Type:** schema

Subtraction of two numbers

### `ogc.openeo.processes.math.sum` — Sum

**Type:** schema

Compute the sum by adding up numbers

### `ogc.openeo.processes.math.trigonometric.arccos` — Arccos

**Type:** schema

Inverse cosine

### `ogc.openeo.processes.math.trigonometric.arcosh` — Arcosh

**Type:** schema

Inverse hyperbolic cosine

### `ogc.openeo.processes.math.trigonometric.arcsin` — Arcsin

**Type:** schema

Inverse sine

### `ogc.openeo.processes.math.trigonometric.arctan` — Arctan

**Type:** schema

Inverse tangent

### `ogc.openeo.processes.math.trigonometric.arctan2` — Arctan2

**Type:** schema

Inverse tangent of two numbers

### `ogc.openeo.processes.math.trigonometric.arsinh` — Arsinh

**Type:** schema

Inverse hyperbolic sine

### `ogc.openeo.processes.math.trigonometric.artanh` — Artanh

**Type:** schema

Inverse hyperbolic tangent

### `ogc.openeo.processes.math.trigonometric.cos` — Cos

**Type:** schema

Cosine

### `ogc.openeo.processes.math.trigonometric.cosh` — Cosh

**Type:** schema

Hyperbolic cosine

### `ogc.openeo.processes.math.trigonometric.sin` — Sin

**Type:** schema

Sine

### `ogc.openeo.processes.math.trigonometric.sinh` — Sinh

**Type:** schema

Hyperbolic sine

### `ogc.openeo.processes.math.trigonometric.tan` — Tan

**Type:** schema

Tangent

### `ogc.openeo.processes.math.trigonometric.tanh` — Tanh

**Type:** schema

Hyperbolic tangent

### `ogc.openeo.processes.texts.eq` — EQ

**Type:** schema

Equal to comparison

### `ogc.openeo.processes.texts.neq` — NEQ

**Type:** schema

Not equal to comparison

### `ogc.openeo.processes.texts.text_begins` — Text begins

**Type:** schema

Text begins with another text

### `ogc.openeo.processes.texts.text_concat` — Text concat

**Type:** schema

Concatenate elements to a single text

### `ogc.openeo.processes.texts.text_contains` — Text contains

**Type:** schema

Text contains another text

### `ogc.openeo.processes.texts.text_ends` — Text ends

**Type:** schema

Text ends with another text

### `ogc.openeo.types.duration` — OpenEO type: Duration

**Type:** schema

An ISO 8601 duration, e.g. P1D for one day.

### `ogc.openeo.types.input-format` — OpenEO type: Input File Format

**Type:** schema

The identifier of a file format supported by the back-end for importing data.

### `ogc.openeo.types.input-format-options` — OpenEO type: Options for Input File Formats

**Type:** schema

Key-value pairs of options for a given input file format.

### `ogc.openeo.types.labeled-array` — OpenEO type: Array with labels

**Type:** schema

An ordered, associative array: a list of values with a label attached to each value.

### `ogc.openeo.types.raster-cube` — OpenEO type: Raster data cube

**Type:** schema

A raster data cube (deprecated in favour of `datacube`).

### `ogc.openeo.types.stac` — OpenEO type: STAC resource

**Type:** schema

A STAC Catalog, Collection, or Item.

### `ogc.openeo.types.vector-cube` — OpenEO type: Vector data cube

**Type:** schema

A vector data cube (deprecated in favour of `datacube`).

### `ogc.openeo.types.workspace-id` — OpenEO type: Workspace ID

**Type:** schema

An identifier for a workspace known to the back-end.

### `ogc.openeo.processes.arrays.array_apply` — Array apply

**Type:** schema

Apply a process to each array element

### `ogc.openeo.processes.arrays.array_filter` — Array filter

**Type:** schema

Filter an array based on a condition

### `ogc.openeo.processes.arrays.count` — Count

**Type:** schema

Count the number of elements

### `ogc.openeo.types.metadata-filter` — OpenEO type: Filters

**Type:** schema

A set of metadata property filters, each expressed as a callback (child process).

### `ogc.openeo.processes.aggregate.aggregate_temporal_period` — Aggregate temporal period

**Type:** schema

Temporal aggregations based on calendar hierarchies

### `ogc.openeo.processes.climatology.anomaly` — Anomaly

**Type:** schema

Compute anomalies

### `ogc.openeo.processes.cubes.add_dimension` — Add dimension

**Type:** schema

Add a new dimension

### `ogc.openeo.processes.cubes.apply` — Apply

**Type:** schema

Apply a process to each value

### `ogc.openeo.processes.cubes.apply_dimension` — Apply dimension

**Type:** schema

Apply a process to all values along a dimension

### `ogc.openeo.processes.cubes.apply_polygon` — Apply polygon

**Type:** schema

Apply a process to segments of the data cube

### `ogc.openeo.processes.cubes.dimension_labels` — Dimension labels

**Type:** schema

Get the dimension labels

### `ogc.openeo.processes.cubes.drop_dimension` — Drop dimension

**Type:** schema

Remove a dimension

### `ogc.openeo.processes.cubes.filter_labels` — Filter labels

**Type:** schema

Filter dimension labels based on a condition

### `ogc.openeo.processes.cubes.mask` — Mask

**Type:** schema

Apply a raster mask

### `ogc.openeo.processes.cubes.merge_cubes` — Merge cubes

**Type:** schema

Merge two data cubes

### `ogc.openeo.processes.cubes.reduce_dimension` — Reduce dimension

**Type:** schema

Reduce dimensions

### `ogc.openeo.processes.cubes.rename_dimension` — Rename dimension

**Type:** schema

Rename a dimension

### `ogc.openeo.processes.cubes.rename_labels` — Rename labels

**Type:** schema

Rename dimension labels

### `ogc.openeo.processes.cubes.resample_cube_spatial` — Resample cube spatial

**Type:** schema

Resample the spatial dimensions to match a target data cube

### `ogc.openeo.processes.cubes.resample_cube_temporal` — Resample cube temporal

**Type:** schema

Resample temporal dimensions to match a target data cube

### `ogc.openeo.processes.cubes.trim_cube` — Trim cube

**Type:** schema

Remove dimension labels with no-data values

### `ogc.openeo.processes.arrays.order` — Order

**Type:** schema

Get the order of array elements

### `ogc.openeo.processes.arrays.sort` — Sort

**Type:** schema

Sort data

### `ogc.openeo.processes.date-and-time.date_shift` — Date shift

**Type:** schema

Manipulates dates and times by addition or subtraction

### `ogc.openeo.processes.comparison.date_between` — Date between

**Type:** schema

Between comparison for dates and times

### `ogc.openeo.processes.cubes.aggregate_spatial` — Aggregate spatial

**Type:** schema

Zonal statistics for geometries

### `ogc.openeo.processes.cubes.filter_spatial` — Filter spatial

**Type:** schema

Spatial filter raster data cubes using geometries

### `ogc.openeo.processes.cubes.mask_polygon` — Mask polygon

**Type:** schema

Apply a polygon mask

### `ogc.openeo.processes.cubes.apply_kernel` — Apply kernel

**Type:** schema

Apply a spatial convolution with a kernel

### `ogc.openeo.processes.cubes.climatological_normal` — Climatological normal

**Type:** schema

Compute climatology normals

### `ogc.openeo.types.temporal-interval` — OpenEO type: Single temporal interval

**Type:** schema

A single left-closed temporal interval, as a two-element array [start, end].

### `ogc.openeo.processes.cubes.filter_bands` — Filter bands

**Type:** schema

Filter the bands by names

### `ogc.openeo.processes.cubes.ndvi` — Ndvi

**Type:** schema

Normalized Difference Vegetation Index

### `ogc.openeo.processes.cubes.resample_spatial` — Resample spatial

**Type:** schema

Resample and warp the spatial dimensions

### `ogc.openeo.types.bounding-box` — OpenEO type: Bounding Box

**Type:** schema

A spatial bounding box given as west/south/east/north extents and an optional CRS.

### `ogc.openeo.types.file-paths` — OpenEO type: Multiple File paths

**Type:** schema

An array of relative paths to user-uploaded files.

### `ogc.openeo.processes.cubes.run_udf` — Run udf

**Type:** schema

Run a UDF

### `ogc.openeo.processes.cubes.save_result` — Save result

**Type:** schema

Save processed data

### `ogc.openeo.types.chunk-size` — OpenEO type: Chunk Size

**Type:** schema

A per-dimension chunk size specification for tiling/processing hints.

### `ogc.openeo.processes.cubes.filter_temporal` — Filter temporal

**Type:** schema

Temporal filter based on temporal intervals

### `ogc.openeo.types.temporal-intervals` — OpenEO type: Multiple temporal intervals

**Type:** schema

An array of (possibly overlapping) temporal intervals.

### `ogc.openeo.processes.cubes.filter_bbox` — Filter bbox

**Type:** schema

Spatial filter using a bounding box

### `ogc.openeo.processes.cubes.load_collection` — Load collection

**Type:** schema

Load a collection

### `ogc.openeo.processes.cubes.apply_neighborhood` — Apply neighborhood

**Type:** schema

Apply a process to pixels in a n-dimensional neighborhood

### `ogc.openeo.processes.cubes.aggregate_temporal` — Aggregate temporal

**Type:** schema

Temporal aggregations

