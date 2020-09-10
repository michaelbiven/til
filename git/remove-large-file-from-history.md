# Remove large file from git history

After commiting a large file into a branch that exceeded GitHubs file size limit, I couldn't push the branch even after removing the file. 

To unblock the push I needed to remove the file from the history of the branch with [filter-branch](https://git-scm.com/docs/git-filter-branch).

`git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch path/to/large/file' --prune-empty --tag-name-filter cat -- --all`
