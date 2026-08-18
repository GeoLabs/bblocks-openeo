
# Load collection (Schema)

`ogc.openeo.processes.cubes.load_collection` *v0.1*

Load a collection

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`load_collection`](https://processes.openeo.org/#load_collection) — *Load a collection*. It models the `arguments` object of a process graph node invoking `load_collection`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Loads a collection from the current back-end by its id and returns it as a processable data cube. The data that is added to the data cube can be restricted with the parameters `spatial_extent`, `temporal_extent`, `bands` and `properties`. If no data is available for the given extents, a `NoDataAvailable` exception is thrown.

**Remarks:**

* All dimensions that specify nominal dimension labels (e.g. bands) are ordered as specified in the data cube metadata (`cube:dimensions`) unless otherwise specified in a corresponding parameter (e.g. `bands`).
* If no additional parameter is specified this would imply that the whole data set is expected to be loaded. Due to the large size of many data sets, this is not recommended and may be optimized by back-ends to only load the data that is actually required after evaluating subsequent processes such as filters. This means that the values in the data cube should be processed only after the data has been limited to the required extent and as a consequence also to a manageable size.
* The scale and offset are not applied automatically when loading the data. If the corresponding STAC properties are present in the collection metadata, they need to be applied explicitly in the UDP.

## Data cube dimension requirements

- `spatial_extent` (a `datacube`): must include a dimension matching `geometry`, per the OpenEO process definition (not enforced by the `datacube` shared type's schema itself, which is deliberately dimension-agnostic).

## Exceptions

- `NoDataAvailable`: There is no data available for the given extents.
- `TemporalExtentEmpty`: The temporal extent is empty. The second instant in time must always be greater/later than the first instant in time.

## Source

OpenEO Processes specification: [`load_collection`](https://processes.openeo.org/#load_collection) ([openeo-processes/load_collection.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/load_collection.json)).

## Examples

### Example 1
Loading `Sentinel-2B` data from a `Sentinel-2` collection for 2018, but only with cloud cover between 0 and 50%.

Example arguments for calling `load_collection`.
#### json
```json
{
  "id": "Sentinel-2",
  "spatial_extent": {
    "west": 16.1,
    "east": 16.6,
    "north": 48.6,
    "south": 47.2
  },
  "temporal_extent": [
    "2018-01-01",
    "2019-01-01"
  ],
  "properties": {
    "eo:cloud_cover": {
      "process_graph": {
        "cc": {
          "process_id": "between",
          "arguments": {
            "x": {
              "from_parameter": "value"
            },
            "min": 0,
            "max": 50
          },
          "result": true
        }
      }
    },
    "platform": {
      "process_graph": {
        "pf": {
          "process_id": "eq",
          "arguments": {
            "x": {
              "from_parameter": "value"
            },
            "y": "Sentinel-2B",
            "case_sensitive": false
          },
          "result": true
        }
      }
    }
  }
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Load a collection
type: object
properties:
  id:
    $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/collection-id/schema.yaml
  spatial_extent:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/bounding-box/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/geojson/schema.yaml
      deprecated: true
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/datacube/schema.yaml
    - title: No filter
      description: Don't filter spatially. All data is included in the data cube.
      type: 'null'
  temporal_extent:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/temporal-interval/schema.yaml
    - title: No filter
      description: Don't filter temporally. All data is included in the data cube.
      type: 'null'
  bands:
    anyOf:
    - type: array
      minItems: 1
      items:
        $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/band-name/schema.yaml
    - title: No filter
      description: Don't filter bands. All bands are included in the data cube.
      type: 'null'
  properties:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/metadata-filter/schema.yaml
    - title: No filter
      description: Don't filter by metadata properties.
      type: 'null'
required:
- id
- spatial_extent
- temporal_extent

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/load_collection/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/cubes/load_collection/schema.yaml)

## Sources

* [OpenEO Processes — load_collection](https://processes.openeo.org/#load_collection)
* [Open-EO/openeo-processes — load_collection.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/load_collection.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/cubes/load_collection`

