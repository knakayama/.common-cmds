Git
===

```bash
# http://qiita.com/digdagdag/items/e577611a032abc148664

# list Authors
$ git shortlog --summary --email

# count added and deleted lines
$ git log --numstat --pretty='%H' | awk 'NF==3 {a+=$1; d+=$2} END {printf("+%d, -%d\n", a, d)}'

# count commits
$ git log --oneline --no-merges | wc -l
```

