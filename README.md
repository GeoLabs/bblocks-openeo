# OpenEO Building Blocks

An investigation into representing the [OpenEO](https://openeo.org) process catalogue — an OGC
Community Standard — as [OGC Building Blocks](https://ogcincubator.github.io/bblocks-docs/). Each
Building Block in this registry is a **proposed schema correspondence** for one OpenEO process or
shared subtype, offered for review — not a settled equivalence between OpenEO and OGC.

## About this registry

This is a new registry (built from the [`bblock-template`](https://github.com/opengeospatial/bblock-template)),
not a fork of an existing one. It models the stable processes of the
[OpenEO Processes specification](https://processes.openeo.org/) — sourced from
[Open-EO/openeo-processes](https://github.com/Open-EO/openeo-processes) at tag `2.0.0-rc.2` — as
OGC Building Block JSON schemas:

- **118 stable OpenEO processes**, one Building Block each, grouped by OpenEO's own native process
  categories under [`_sources/processes/<category>/`](_sources/processes) (e.g. `arrays`, `math`,
  `cubes`, `comparison`, ...). Experimental processes under openeo-processes' `proposals/` are out
  of scope for this pass.
- **33 shared OpenEO subtype schemas** (data cubes, process graphs, bounding boxes, temporal
  intervals, band names, ...) under [`_sources/types/`](_sources/types), modelled once and reused
  by `$ref` across process Building Blocks, instead of duplicating the same fragment ~100 times.

Each process Building Block's `schema.yaml` describes the `arguments` object of a process graph
node invoking that OpenEO process; `description.md` links back to the authoritative
[processes.openeo.org](https://processes.openeo.org/) entry and the exact source file at the pinned
tag. No semantic uplift (JSON-LD context) or SHACL validation is included in this pass — see
[Status and non-goals](#status-and-non-goals) below.

## Relationship to OSPD 2026 D100 Activity 4

This registry is produced by GeoLabs SARL under **OSPD 2026, D100 Activity 4**: population of a
Building Blocks registry and mapping proposals towards OpenEO terms. It is documented as an open
investigation, consistent with the tone already established for the D100 bid: each OpenEO ⇄ OGC
correspondence is a proposal to be reviewed, not a finished standardization outcome.

## Six-phase workflow mapping

[`docs/six-phases-mapping.md`](docs/six-phases-mapping.md) maps every Building Block in this
registry onto GeoLabs' six-phase workflow profiling framework (D100 Activity 2, used for the W1/W2
workflow analysis): filter configuration → selection/filtering → data retrieval → pre-processing →
scientific computation → export/aggregation. This mapping was produced *after* the registry was
built and validated, and does not constrain the Building Blocks' own structure — it is a separate,
equally provisional, cross-reference.

## Repository structure

```text
_sources/
  types/                          shared OpenEO subtype schemas (33)
  processes/
    <category>/                   one directory per OpenEO native category
      <process-id>/
        bblock.json                metadata
        description.md             human-readable description, links to processes.openeo.org
        schema.yaml                JSON Schema for the process's `arguments` object
        examples.yaml               at least one example per Building Block
docs/
  six-phases-mapping.md           see above
build/                             generated output — never edited by hand
```

## Building and viewing locally

```shell
docker run -it --pull=always --rm --workdir /workspace -v "$(pwd):/workspace" \
  ghcr.io/opengeospatial/bblocks-postprocess --clean true --base-url http://localhost:9090/register/

docker run --rm --pull=always -v "$(pwd):/register" -p 9090:9090 ghcr.io/ogcincubator/bblocks-viewer
```

See [`USAGE.md`](USAGE.md) (inherited from `bblock-template`) for details on the Building Block
file format, imports, and the postprocessing/validation pipeline.

## Status and non-goals

- All Building Blocks are `status: under-development`.
- No RDF/SHACL semantic uplift yet — this is a schema-first pass, deferred to a later iteration.
- No pull request to an upstream register — this is a standalone registry, not a contribution to
  an existing one.
