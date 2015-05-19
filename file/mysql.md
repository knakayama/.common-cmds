MySQL
=====

```bash
# innodb fragmentation
$ mysql -uroot -e "SELECT TABLE_SCHEMA, SUM(data_length+index_length) / 1024 / 1024 / 1024 AS 'Size (GB)' FROM information_schema.tables WHERE table_schema = '<database>';"
```

