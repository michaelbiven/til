# Show remote origin for a git repo

`git config --get remote.origin.url`

Display the name of each repo and it's origin URL: 
`for f in $(ls -d */); do  u="$(git config --file ./${f}/.git/config --get remote.origin.url)"; echo "Repo: ${f} Origin: ${u}" ; done`

