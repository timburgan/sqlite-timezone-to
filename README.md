# `timezone_to`<br>SQLite Timezone Extension 
<center><code>timezone_to(DATETIME('2025-01-01 16:33:22'), 'UTC', 'Australia/Sydney')</code></center>


## Overview

`timezone_to` is an SQLite extension that enables seamless timezone conversion within SQLite queries. It enables timezone-aware timestamps directly in SQLite, that SQLite doesn't otherwise support beyond [localtime or UTC](https://sqlite.org/lang_datefunc.html).


### Usage examples
```sql
SELECT timezone_to('2025-04-10 14:00', 'America/New_York', 'Europe/London');
-- Output: '2025-04-10 19:00:00'

SELECT timezone_to(datetime('2025-04-10 14:00'), 'America/New_York', 'Europe/London');
-- Output: '2025-04-10 19:00:00'

-- what's current time in Sydney?
SELECT timezone_to(datetime('now'), 'UTC', 'Australia/Sydney');

-- or
SELECT timezone_to(datetime('now', 'localtime'), 'America/New_York',  'Australia/Sydney');
```


## Installation

1. Download the [latest release](https://github.com/timburgan/sqlite-timezone-to/releases) `.so` file.  
   _Available via sidebar on this repo._
2. Load `.so` file to SQLite using one of the [standard methods](https://sqlite.org/loadext.html) once SQLite is loaded:

    ```sql
    -- open your database
    sqlite3 example-db.sqlite3

    -- either
    .load ./path/to/timezone_to.so

    -- or
    SELECT sqlite3_load_extension('./path/to/timezone_to.so');
    ```

3. Ready to use.


## Dependencies

This requires your SQLite database to be running on Debian or Ubuntu-like systems. The timezone database is deferred to the OS.


## License

Personal use is free.  
License is needed for business related or commercial use. 

- There is free unlimited usage for 30 days, at which time the license will be verified.
- Licensed use is USD $99.  
- [Purchase directly here](https://buy.polar.sh/polar_cl_dIbDAfuEjkzOZiAhtt1yjhiH2EIIzeEdMBMAn0VkszJ). A license key will be emailed to you immediately.

Apply license with:

> ```sql
> SELECT set_timezone_to_license(<key>, <name>);
> ```
> 
> or OS environment variable:
> 
> ```bash
> SQLITE_TIMEZONE_TO_LICENSE=<key>:<name>
> ```


## Support

License holder support at [sqlite@timburgan.com](mailto:sqlite@timburgan.com)

