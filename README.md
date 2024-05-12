# git-aliases
Storing my favorite Git aliases where I can easily access them.

```ini
s = status
c = "!git add . && git commit -m"
co = checkout
cob = checkout -b
com = checkout main
pom = pull origin main
upmain = "!git com && git pom"
new = "!git com && git pom && git cob"
del = branch -D
rename = branch -m
diffn = diff --name-only main...HEAD
diffx = diff --full-index main
diffxo = "!git diffx > output.diff"
clear = "!git checkout -- . && git clean -f"
rim = rebase -i main
upbase = "!git com && git pom && git co - && git rim"
upmerge = "!git fetch && git merge origin/main"
pusho = !git push origin $(git rev-parse --abbrev-ref)
res = reset --hard HEAD~1
publish = "!git upbase && git upremote"
br="!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"
upremote = "!git push --delete origin $(git rev-parse --abbrev-ref HEAD) && git push origin $(git rev-parse --abbrev-ref HEAD)"
history = "!git log --author=\"William Baldoumas\""
delete-stale = "!git branch --format='%(refname:short) %(committerdate:relative)' --sort=committerdate | awk '$1 != \"main\" && $2~/^.* days ago$/ && $2 > \"'$1' days ago\" {print $1}' | xargs -r git branch -D"
lol = log --graph --decorate --pretty=oneline --abbrev-commit
aliases = config --get-regexp alias
```
