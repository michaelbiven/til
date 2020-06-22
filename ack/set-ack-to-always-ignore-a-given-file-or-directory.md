# set ack to always ignore a given file or directory

`ack`  can ignore a given list of directories, files, or file types. 

`--[no]ignore-dir=name         Add/remove directory from list of ignored dirs`

`--ignore-file=FILTER:ARGS     Add filter for ignoring files.`

`-T X, --type=noX              Exclude X files, where X is a filetype.`

For example in my [`.ackrc`](https://github.com/michaelbiven/dotfiles/blob/master/.ackrc) I'm ignoring several Terraform directories.


```
$ cat ~/.ackrc
# sort by filename
--sort-files

# case
--ignore-case
--smart-case

# display
# Run ack --help-colors for a list of possible color combinations.
--color-filename=bright_green
--color-match=bright_yellow
--color-lineno=bright_blue

# filetypes
# Run ack --help-types for a list of all known types, and how they're defined.
--type-add=terraform=.tf,.tfvars

# ignores
--ignore-directory=is:.terraform
--ignore-directory=is:terraform.tfstate.d
--ignore-file=ext:.tfplan
--ignore-file=is:terraform.tfstate
--ignore-file=is:terraform.tfstate.backup
--ignore-directory=is:node_modules
```

