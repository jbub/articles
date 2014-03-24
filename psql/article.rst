psql
====

Basic info about user tables
----------------------------

.. code-block:: python
    
    SELECT relname, seq_scan, idx_scan, last_autovacuum, last_autoanalyze, autovacuum_count, autoanalyze_count FROM pg_stat_user_tables;
