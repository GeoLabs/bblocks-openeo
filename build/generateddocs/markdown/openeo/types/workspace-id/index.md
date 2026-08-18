
# OpenEO type: Workspace ID (Schema)

`ogc.openeo.types.workspace-id` *v0.1*

An identifier for a workspace known to the back-end.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO shared subtype `workspace-id`, as defined in the [OpenEO Processes subtype schemas](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json). It is a candidate correspondence, not a settled equivalence to any existing OGC schema.

A workspace identifier from the list of available workspaces.

## Examples

### Example value
An identifier for a back-end workspace.
#### json
```json
"my-workspace"
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: string
subtype: workspace-id
title: Workspace ID
description: A workspace identifier from the list of available workspaces.
pattern: ^[\w\-\.~]+$

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/workspace-id/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/workspace-id/schema.yaml)

## Sources

* [OpenEO Processes — subtype-schemas.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/meta/subtype-schemas.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/types/workspace-id`

