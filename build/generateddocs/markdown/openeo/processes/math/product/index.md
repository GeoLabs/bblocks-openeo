
# Product (Schema)

`ogc.openeo.processes.math.product` *v0.1*

Compute the product by multiplying numbers

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`product`](https://processes.openeo.org/#product) — *Compute the product by multiplying numbers*. It models the `arguments` object of a process graph node invoking `product`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Multiplies all elements in a sequential array of numbers and returns the computed product.

The computations follow [IEEE Standard 754](https://ieeexplore.ieee.org/document/8766229) whenever the processing environment supports it.

An array with solely no-data values returns the no-data value (or `null`).

## Source

OpenEO Processes specification: [`product`](https://processes.openeo.org/#product) ([openeo-processes/product.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/product.json)).

## Examples

### Example 1
Calling `product` with these arguments returns `0`.
#### json
```json
{
  "data": [
    5,
    0
  ]
}
```


### Example 2
Calling `product` with these arguments returns `-20`.
#### json
```json
{
  "data": [
    -2,
    4,
    2.5
  ]
}
```


### Example 3
Calling `product` with these arguments returns `null`.
#### json
```json
{
  "data": [
    1,
    null
  ],
  "ignore_nodata": false
}
```


### Example 4
Calling `product` with these arguments returns `-1`.
#### json
```json
{
  "data": [
    -1
  ]
}
```


### Example 5
Calling `product` with these arguments returns `null`.
#### json
```json
{
  "data": [
    null
  ],
  "ignore_nodata": false
}
```


### Example 6
Calling `product` with these arguments returns `null`.
#### json
```json
{
  "data": []
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Compute the product by multiplying numbers
type: object
properties:
  data:
    type: array
    items:
      type:
      - number
      - 'null'
  ignore_nodata:
    type: boolean
required:
- data

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/product/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/math/product/schema.yaml)

## Sources

* [OpenEO Processes — product](https://processes.openeo.org/#product)
* [Open-EO/openeo-processes — product.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/product.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/math/product`

