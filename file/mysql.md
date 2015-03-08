MySQL
=====

```bash
# innodb fragmentation
$ mysql -uroot -e "select table_schema, sum(data_length+index_length) / 1024 / 1024 / 1024 as 'Size (GB)' from information_schema.tables where table_schema = '<table>';"
```

