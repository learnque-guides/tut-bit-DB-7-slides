# When not to use indexes?

When data is written to the database, the original table is updated first and then all of the indexes off of that table are updated. Every time a write is made to the database, the indexes are unusable until they have updated. If the database is constantly receiving writes then the indexes will never be usable. This is why indexes are typically applied to databases in data warehouses that get new data updated on a scheduled basis (off-peak hours) and not production databases which might be receiving new writes all the time.
