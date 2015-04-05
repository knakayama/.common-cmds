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

# ignore newline diff
$ git diff -w

# only list tags which contain the specified commit (HEAD if not specified)
$ git tag --contains=<commit-id>

# show only names and status of changed files
$ git log --name-status

# remove merged branch
# http://gutch.hatenablog.com/entry/2014/05/17/155840
$ git branch --merged | grep -vF '*' | xargs -n1 -t git brnach -d

# add new URL
$ git remote set-url --add <url>

# remove untracked files from the working tree
$ git clean -d --dry-run
$ git clean -d --force
```

