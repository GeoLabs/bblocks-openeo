
# Date shift (Schema)

`ogc.openeo.processes.date-and-time.date_shift` *v0.1*

Manipulates dates and times by addition or subtraction

[*Status*](http://www.opengis.net/def/status): Under development

## Description

This Building Block proposes a schema representation of the OpenEO process [`date_shift`](https://processes.openeo.org/#date_shift) — *Manipulates dates and times by addition or subtraction*. It models the `arguments` object of a process graph node invoking `date_shift`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Based on a given date (and optionally time), calculates a new date (and time if given) by adding or subtracting a given temporal period.

Some specifics about dates and times need to be taken into account:

* This process doesn't have any effect on the time zone.
* It doesn't take daylight saving time (DST) into account as only dates and times in UTC (with potential numerical time zone modifier) are supported.
* Leap years are implemented in a way that computations handle them gracefully (see parameter `unit` for details).
* Leap seconds are mostly ignored in manipulations as they don't follow a regular pattern. Leap seconds can be passed to the process, but will never be returned.

## Source

OpenEO Processes specification: [`date_shift`](https://processes.openeo.org/#date_shift) ([openeo-processes/date_shift.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_shift.json)).

## Examples

### Example 1
Calling `date_shift` with these arguments returns `"2020-08-01T17:22:45Z"`.
#### json
```json
{
  "date": "2020-02-01T17:22:45Z",
  "value": 6,
  "unit": "month"
}
```


### Example 2
Calling `date_shift` with these arguments returns `"2021-03-24T00:00:00+02:00"`.
#### json
```json
{
  "date": "2021-03-31T00:00:00+02:00",
  "value": -7,
  "unit": "day"
}
```


### Example 3
Adding a year to February 29th in a leap year will result in February 28th in the next (non-leap) year.

Calling `date_shift` with these arguments returns `"2021-02-28T17:22:45Z"`.
#### json
```json
{
  "date": "2020-02-29T17:22:45Z",
  "value": 1,
  "unit": "year"
}
```


### Example 4
Adding a month to January 31th will result in February 29th in leap years.

Calling `date_shift` with these arguments returns `"2020-02-29"`.
#### json
```json
{
  "date": "2020-01-31",
  "value": 1,
  "unit": "month"
}
```


### Example 5
The process skips over the leap second `2016-12-31T23:59:60Z`.

Calling `date_shift` with these arguments returns `"2017-01-01T00:00:00Z"`.
#### json
```json
{
  "date": "2016-12-31T23:59:59Z",
  "value": 1,
  "unit": "second"
}
```


### Example 6
Milliseconds can be added or subtracted. If not given, the default value is `0`.

Calling `date_shift` with these arguments returns `"2018-12-31T17:22:46.150Z"`.
#### json
```json
{
  "date": "2018-12-31T17:22:45Z",
  "value": 1150,
  "unit": "millisecond"
}
```


### Example 7
Calling `date_shift` with these arguments returns `"2018-01-02"`.
#### json
```json
{
  "date": "2018-01-01",
  "value": 25,
  "unit": "hour"
}
```


### Example 8
Calling `date_shift` with these arguments returns `"2017-12-31"`.
#### json
```json
{
  "date": "2018-01-01",
  "value": -1,
  "unit": "hour"
}
```

## Schema

```yaml
$schema: https://json-schema.org/draft/2020-12/schema
description: Manipulates dates and times by addition or subtraction
type: object
properties:
  date:
    anyOf:
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date-time/schema.yaml
    - $ref: https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/types/date/schema.yaml
  value:
    type: integer
  unit:
    type: string
    enum:
    - millisecond
    - second
    - minute
    - hour
    - day
    - week
    - month
    - year
required:
- date
- value
- unit

```

Links to the schema:

* YAML version: [schema.yaml](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/date-and-time/date_shift/schema.json)
* JSON version: [schema.json](https://raw.githubusercontent.com/GeoLabs/bblocks-openeo/undefined/build/annotated/openeo/processes/date-and-time/date_shift/schema.yaml)

## Sources

* [OpenEO Processes — date_shift](https://processes.openeo.org/#date_shift)
* [Open-EO/openeo-processes — date_shift.json (2.0.0-rc.2)](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_shift.json)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/GeoLabs/bblocks-openeo](https://github.com/GeoLabs/bblocks-openeo)
* Path: `_sources/processes/date-and-time/date_shift`

