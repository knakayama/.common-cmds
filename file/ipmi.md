IPMI
====

```bash
# BMC cold reset
$ IPMICFG -r
```

```bash
# show ipmi info (voltage etc..)
$ IPMICFG -pminfo
```

```bash
# [1282611]
$ ipmitool lan set 1 auth Admin MD5,PASSWORD
$ ipmitool lan set 1 auth Operator MD5,PASSWORD
$ ipmitool lan set 1 auth User MD5,PASSWORD
$ ipmitool lan set 1 auth Callback MD5,PASSWORD
```

```bash
# check user list
$ ipmitool user list 1
# set user name
$ ipmitool user set name 3 ADMIN
# set user password
$ ipmitool user set password 3 ADMIN
$ ipmitool user enable 3
$ ipmitool user priv 3 4 1
```

