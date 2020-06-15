# Merging two git repositories

Example: Merge `repo-one` into `repo-two`.

1. cd into `repo-two`
2. `git remote add -f repo-one  path/or/link/to/repo-one`
3. `git merge --allow-unrelated-histories repo-one/master`

