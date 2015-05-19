MySQL
=====

```bash
# innodb fragmentation
$ mysql -uroot -e "SELECT TABLE_SCHEMA, SUM(data_length+index_length) / 1024 / 1024 / 1024 AS 'Size (GB)' FROM information_schema.tables WHERE table_schema = '<database>';"
# over 100MB
$ ls -lS /home/mysql/<database> | awk '$5>=100000000 {print $NF}' | xargs -I% ls -l /home/mysql/<database>/%
```
