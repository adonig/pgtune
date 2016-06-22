pgtune
======

A tool to optimize PostgreSQL for *[OSM2Vectortiles](http://osm2vectortiles.org/)* (DW) workloads.

Usage:
------
```
$ ./pgtune.py -c 20 ->> /var/lib/pgsql/9.x/data/postgresql.conf
```

Example output:
--------------
```
./pgtune.py -c 20 -S
#
# OSM2Vectortiles friendly configuration for PostgreSQL 9.5
#
# Config for 7GB memory and 20 connections
#
checkpoint_completion_target = 0.9
default_statistics_target = 1000
effective_cache_size = 5GB
maintenance_work_mem = 486MB
max_connections = 20
max_wal_size = 4GB
min_wal_size = 1GB
shared_buffers = 1GB
synchronous_commit = off
vacuum_cost_delay = 50
wal_buffers = 16MB
wal_compression = on
wal_writer_delay = 10s
work_mem = 97MB
#
# other goodies
#
log_line_prefix = '%m <%d %u %a %r> %%'
log_temp_files = 0
log_min_duration_statement = 20
log_checkpoints = on
log_lock_waits = on
listen_addresses = 'localhost'
shared_preload_libraries = 'pg_stat_statements'

```


LICENSE
-------
This work is based on https://github.com/kofemann/pgtune and published under [public domain](https://creativecommons.org/licenses/publicdomain/) license.

