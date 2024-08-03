# Stash 

stash is storing pending changes (in form of stack) temporarily before committed.

``` bash
git stash  # put pending changes state into stash
git stash list # show pending changes that are stored in stash

git stash apply # apply first item of pending changes store in stash to files

git stash pop   # apply first item of pending changes store in stash to files and remove it from stash list

git stash drop # remove/delete first element on index 0 of stash

git stash branch "branch_name_new" # create new branch and
                                   # apply first element of stash on the new branch
```
### NOTE :

*) New file(s) that are untracked (not add to git yet), can not be added to stash


**CASE**
<br/>commit changes of one brach to another branch

``` bash
$ git stash
$ git checkout other-branch
$ git stash pop

#maybe need git mergetool
$ git mergetool

$ git add .
$ git commit -m "...."
$ git push

$ git checkout original-branch
$ git stash pop

# if want to reset
$ git reset --hard
```
