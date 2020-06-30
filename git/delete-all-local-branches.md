# Delete All Local Branches

A simple one-liner to delete all local branches that have been merged with the `master` branch. And it will not delete anything that hasn't been merged.

`$ git branch --merged master | grep -v master | xargs git branch -d`

If you're sure you want to also delete everything use the `-D` option for `git branch`.

`$ git branch --merged master | grep -v master | xargs git branch -D`

