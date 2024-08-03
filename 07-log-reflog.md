#   Log  

``` bash
git log
git log --oneline
git log --oneline | wc -l
git log --oneline --graph

git log master # show log of branch master
git log origin/master # show log on remote origin branch master

git shortlog --summary --numbered --email


git log --all --graph --oneline --decorate
git log --branches --tags --remotes --graph --oneline --decorate

#To search the commit log (across all branches) for the given text:
git log --all --grep='Build 0051'

# in case your commit is dangling and not connected to history at all, you can search the reflog itself with the -g flag (short for --walk-reflogs:
git log -g --grep='Build 0051'
```

# RefLog 
``` bash
git reflog  # show all log where HEAD was used to referenced.
```
