---
title: GIT
sidebar_name: GIT
description: GIT commands
keywords: git, igthub
---

## Submodules

```sh
git submodule update --recursive --init
```

## Reset history of a repo

```sh
git checkout --orphan newBranch
git add -A  # Add all files and commit them
git commit
git branch -D master  # Deletes the master branch
git branch -m master  # Rename the current branch to master
git push -f origin master  # Force push master branch to github
git gc --aggressive --prune=all     # remove the old files
```

> - [https://stackoverflow.com/a/13102849](https://stackoverflow.com/a/13102849)

## See public ssh keys

```url
https://github.com/USERNAME.keys
https://gitlab.com/USERNAME.keys
```

## GIT config

```sh
# show the config
git config --list --global

# change the config
git config --global user.name "n4n5"
```

## Commits stats

```sh
git shortlog -sn
```

## pre-commit

```sh
# install pre-commit
python -m pip install -u pre-commit
# install pre-commit hook
python -m pre_commit install

# useful command
python -m pre_commit run --all-files
```

## Add multiple push URLs

```sh
git remote set-url --add --push [remote] [original_repo_URL]
git remote set-url --add --push [remote] [second_repo_URL]
git remote -v
```

## Change commit date

```sh
changeCommitDate() {
  VARIABLE="${1:-3}"
  printf 'DAT=$(date --date "%s days ago" -R) GIT_AUTHOR_DATE=$DAT GIT_COMMITTER_DATE=$DAT git commit -m "message"\n' "$VARIABLE"
}
```
