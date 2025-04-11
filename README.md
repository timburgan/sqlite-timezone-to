# `timezone_to` SQLite Timezone Extension 
<center><code>timezone_to(DATETIME('2025-01-01 16:33:22'), 'UTC', 'Australia/Sydney')</code></center>


## Overview

`timezone_to` is an SQLite extension that enables seamless timezone conversion within SQLite queries. It enables timezone-aware timestamps directly in SQLite, that SQLite doesn't otherwise support beyond [localtime or UTC](https://sqlite.org/lang_datefunc.html).


### Usage
```sql
SELECT
timezone_to(
  <datetime>, 
  <IANA_timezone_of_that_datetime>, 
  <IANA_timezone_to_convert_the_datetime_to>
);
```

Example
```sql
SELECT timezone_to(datatime('2025-04-10 14:00'), 'America/New_York', 'Europe/London');
-- Output: '2025-04-10 19:00:00'

SELECT timezone_to(datatime('now'), 'UTC', 'Australia/Sydney');

SELECT timezone_to(datatime('now', 'localtime'), 'UTC',  'Australia/Sydney');
```


## Installation

1. Download the latest release file.
2. Load to SQLite.
3. Ready to use.


## License

Personal use is free. License is needed for business related or commercial use. 

There is free unlimited usage for 30 days, at which time the license will be verified.

- Licensed use is USD $99.  
  Purchase at https://example.com/sqlite-timezone-to 

Apply license with:
```
SELECT set_timezone_to_license(<key>, <name>);
```
or OS environment variable:
```
SQLITE_TIMEZONE_TO_LICENSE=<key>:<name>
```


## Support

License holder support at [sqlite@timburgan.com](mailto:sqlite@timburgan.com)

