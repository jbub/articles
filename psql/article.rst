psql
====

Basic info about user tables
----------------------------

- ``relname`` - name of the table
- ``seq_scan`` - number of sequential scans initiated on this table
- ``idx_scan`` - number of index scans initiated on this table
- ``n_live_tup`` - estimated number of live rows
- ``last_autovacuum`` - last time at which this table was vacuumed by the autovacuum daemon
- ``last_autoanalyze`` - last time at which this table was analyzed by the autovacuum daemon
- ``autovacuum_count`` - number of times this table has been vacuumed by the autovacuum daemon
- ``autoanalyze_count`` - Number of times this table has been analyzed by the autovacuum daemon

.. code-block:: sql
    
    SELECT relname, seq_scan, idx_scan, n_live_tup, last_autovacuum, 
           last_autoanalyze, autovacuum_count, autoanalyze_count  FROM pg_stat_user_tables;
