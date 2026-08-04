This Building Block proposes a schema representation of the OpenEO process [`date_shift`](https://processes.openeo.org/#date_shift) — *Manipulates dates and times by addition or subtraction*. It models the `arguments` object of a process graph node invoking `date_shift`. This is a proposed correspondence between the OpenEO process definition and an OGC Building Block schema, not a settled equivalence.

Based on a given date (and optionally time), calculates a new date (and time if given) by adding or subtracting a given temporal period.

Some specifics about dates and times need to be taken into account:

* This process doesn't have any effect on the time zone.
* It doesn't take daylight saving time (DST) into account as only dates and times in UTC (with potential numerical time zone modifier) are supported.
* Leap years are implemented in a way that computations handle them gracefully (see parameter `unit` for details).
* Leap seconds are mostly ignored in manipulations as they don't follow a regular pattern. Leap seconds can be passed to the process, but will never be returned.

## Source

OpenEO Processes specification: [`date_shift`](https://processes.openeo.org/#date_shift) ([openeo-processes/date_shift.json at 2.0.0-rc.2](https://github.com/Open-EO/openeo-processes/blob/2.0.0-rc.2/date_shift.json)).
