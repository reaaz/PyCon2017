# Temporal Data Structures with SQLAlchemy and Postgress by Joey Leingang
1. What does temporal mean?
2. Some things we tried
 * Logging
 * Verisioned tables
 * Per-property tracking
  * current table, friends clock table with friend, tick and timestamp and a location history table
3. Postgres: ranges
 * Containment
 * Overlaps
 * Extract the upper bound
 * Compute the intersection
 * Is the range empty?
4. Postgres: exclusion constraints
 * `btree_gist` extension
 * Location history table stores `vlock` as `int4range`
5. SQLAlchemy
 * `temporal_sqlalchemy` package and `sqlalchemy.ext.declarative` packages
6. If you need to keep history, trade offs apply. This method uses a lot of tables for a lot of models and a lot of properties. Doing things in bulk is very challenging.
