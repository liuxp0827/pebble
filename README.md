# WARNING: Pebble is an incomplete work-in-progress.

# Pebble

Pebble is a LevelDB/RocksDB inspired key-value store focused on
performance and internal usage by CockroachDB. Pebble inherits the
RocksDB file formats and a few extensions such as range deletion
tombstones, whole-table bloom filters, and updates to the MANIFEST
format.

Pebble intentionally does not aspire to include every feature in
RocksDB and is specifically targetting the use case and feature set
needed by CockroachDB:

* Block-based tables
* Indexed batches
* Level-based compaction
* Merge operator
* Prefix bloom filters
* Range deletion tombstones
* Reverse iteration
* SSTable ingestion
* Table-level bloom filters

Pebble may silently corrupt data or behave incorrectly if used with a
RocksDB database that uses a feature Pebble doesn't support. Caveat
emptor!

## Pedigree

Pebble is based on the (at the time of writing) incomplete Go version
of LevelDB:

https://github.com/golang/leveldb

The Go version of LevelDB is based on the C++ original:

https://github.com/google/leveldb