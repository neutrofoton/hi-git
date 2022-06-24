# Config
Set configuration locally and globally

``` bash
git config --global user.name "me"
git config --global user.email "me@gmail.com"

git config --global core.editor vim

git config --global help.autocorrect=1


# to set locally just remove "--global" keyword
git config --list

cat .git/config
```

# Status 
Show git status

``` bash
git status
```

# Add 

``` bash
git add filename.txt
git add -u  # add all updated file to staging area
git add -A  # add ALL file including untracked files to staging area

```

# Commit

``` bash
git commit
git commit -m "comment description here"
git commit -am "comment description here" # git add to updated file and commit with comment
```

``` bash
# commit yang sedang di edit ke branch baru
# https://stackoverflow.com/questions/14655816/how-to-commit-changes-to-a-new-branch/50177571

$ git checkout -b your-new-branch
$ git add <files>
$ git commit -m <message>
``` 

# Diff 
``` bash
git diff aaaaaa..bbbbbb
git diff HEAD~1..HEAD

git diff 34f47ee..3228b37 -- {FileName} # compare specified file between to specific commits
```

# Difftool 
``` bash
git difftool file.m  #diff the local file.m against the checked-in version

git difftool some-feature-branch file.m  # diff the local file.m against the version in some-feature-branch


git difftool Build-54..Build-55 file.m  # diff the file.m from the Build-54 tag to the Build-55 tag

git diff 34f47ee..3228b37 -- {FileName} # compare specified file between to specific commits using difftool
```

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


# Show 
``` bash
git show HEAD
git show HEAD~1
git show xxxxxx(hash number)

git show --pretty --name-status 29c2770b  # show list of changes with their status
git show --pretty --name-only 29c2770b # show list of changes without their status
```

# Checkout 
``` bash
git checkout filename.txt # pull back to HEAD (undo). Can be applied to revert changes

git checkout -- filename # pull back one file (undo)

git checkout abcde file/to/restore # Undo a file to specific commit. Assuming the commit you want is abcde

git checkout "branch_name" # switch working copy to branch "branch_name"

git fetch && git checkout "branch_name" # fetch and switch branch

git checkout tags/{Tag_Name}
```

# Reset 
``` bash
git reset --hard HEAD~1 # reset working copy back to HEAD and remove all changes and undo multiple changes.
git reset --soft HEAD~1 # reset HEAD state to HEAD~1
                          and put all changes previous HEAD to staging area of new HEAD (HEAD~1)


git reset # can be used to undo command : $ git add .
```

# Clean  
``` bash
git clean
git clean -f # clean up working copy and discards any changes in current working copy

```

#  Git Ignore 
``` bash
touch .gitignore
    # /Logs
    # /Log/*.txt
```

# Remote
``` bash
git remote
git remote -v # show git remote url

git remote add origin "url://...." # add remote origin url
git remote rm origin # remove remote origin
```

# Clone 
``` bash
git clone "url://....""
```

# Fetch 
``` bash
git fetch # pull from remote origin.
git fetch origin # pull from remote origin
```

# Pull 
``` bash
git pull # pull from remote origin.
         # It's also a short cut of : $ git fetch; git merge origin/master

git pull origin master # pull from remote origin of branch master

git pull appprojecttemplate master # pull from remote appprojecttemplate of branch master
```

#  Branch
``` bash 
git branch # show branch local
git branch -r # show all branch in remote
git branch -a # show all branch in local

git branch --set-upstream master origin/master # to make correspondence between local master to origin master.

git branch "branch_name" # create local branch
git branch "branch_name" 974b56a # *) create local branch from particular commit of hashing 974b56a
                                    *) if commit of hashing 974b56a is hash of commit that already deleted,
                                       this command will restore the deleted commit and create new branch named "branch_name"

git branch "branch_name" "tag_name" # create branch called "branch_name" based on "tag_name" tag.

git branch -m "branch_name_old" "branch_name_new" # move (rename)  branch_name_old to branch_name_new

git branch -d "branch_name" # delete "branch_name" branch.
git branch -D "branch_name" # delete "branch_name" branch (force delete). This is usually happen to delete branch that has not been merged to master yet.

```
NOTE :
*) --set-upstream  : is upstream tracking branch which means what remote branch does local branch mirror to.

*) brach basically is simply label shown hashed of individual commit

#  tag 
``` bash
git tag => show list of tag available
git tag "tag_name" => add tag with name "tag_name"
git tag -a "tag_name" => add tag with name "tag_name" and add message to it.
git tag -s "tag_name" => add tag with name "tag_name", add message to it and signed the tag with user identity RSA
git tag -v "tag_name" => verified tag
```

NOTE :
1. http://stackoverflow.com/questions/1457103/how-is-a-tag-different-from-a-branch-which-should-i-use-here
A tag represents a version of a particular branch at a moment in time. A branch represents a separate thread of development that may run concurrently with other development efforts on the same code base. Changes to a branch may eventually be merged back into another branch to unify them.

2. Big difference between branch and tag :
    <br/>a. Branch will follow the commit. As we add commit on that branch, the branch will move along
    <br/>
    <br/>b. Tag will stay on the commit. In other word, "tag" is just a friendly name of the shown hash.

# Push 

``` bash
git push # push local commit changes to remote origin.

git push --set-upstream origin master # to make correspondence between local master to origin and create master branch in origin.

git push --tags # push local tags from local to remote origin. By default git does not push tags.

git push --all # push all changes, branches to remote origin.
git push --all -u
    # *) -u, --set-upstream
    #      For every branch that is up to date or successfully pushed, add upstream (tracking) reference,
    # *) git push --all won't push your tags, only your branches.


git push --tags # push all tags

git push origin "branch_name" # push changes and branch_name to remote origin.
                              # Other branches not pushed if any.

git push origin "branch_name_local":"branch_name_remote"
      # *) would push branch_name_local in local as branch_name_remote in remote origin.
      # *) If branch_name_local is empty, it would delete remote branch named branch_name_remote
```
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

# Merge  
``` bash
git merge "branch_name" # merge branch_name to master

git mergetool # open git merge tool to resolve merge conflicts

```

### NOTE :
before merging branch to master, ensure switch to master current work copy first.


# Rebase 
"rebase" will move the entire feature branch to begin on the tip of the master branch, effectively incorporating all of the new commits in master. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch.


``` bash
          A---B---C feature
         /
   D---E---F---G master
   ```

``` bash
git checkout feature;
git rebase master
```

would be:

``` bash

            A'--B'--C' feature
            /
D---E---F---G master


```

``` bash
# *) the two command above will move entire feature branch to begin on the tip of the master branch.
# *) on rebasing process sometime we still need call :

   git mergetool # to solve conflict if any, just like we do on merge command.

git rebase --continue | --skip | --abort | --edit-todo
```

# cherry-pick 

``` bash
git cherry-pick 5904c36 # just pick one commit of hash 5904c36 and apply to current HEAD of branch
```

# Show
``` bash
# show all file committed.
git show --name-only deba979


```


#   Import Code from Other branch 

``` bash
#add remote url named REMOTE.TEMPLATE
git remote add REMOTE.TEMPLATE http://gitserver/repo/app.project.template.git

# fetch from REMOTE.TEMPLATE remote url
git fetch REMOTE.TEMPLATE

#checkout REMOTE.TEMPLATE/master and create a new branch called TEMPLATE
git checkout -b TEMPLATE REMOTE.TEMPLATE/master

#switch back to master branch
git checkout master

# merge TEMPLATE brach to master branch
git merge TEMPLATE

# commit changes
git commit

# remove REMOTE.TEMPLATE remote address
git remote rm REMOTE.TEMPLATE

# remove template branch. It is useful to get rid of the extra branch before pushing
git branch -d TEMPLATE

# push to remote origin/master
git push

``` 
### References:
1. http://stackoverflow.com/questions/1683531/how-to-import-existing-git-repository-into-another


#   CASES 

### Steps excluding files and adding to gitignore for the files that already in git

 
1. tambahkan file atau folder atau extension ke .gitignore
2. jalankan 
    ```bash 
    git rm --cached XXXX. 
    ```

   Contoh :
   ```bash 
   git rm --cached src/directories/Database/*
   git rm --cached -rf src/directories/.idea
    ```

3. maka file2 tsb akan masuk ke untracked. 
4. jalankan git add .
5. commit changes pada .gitignore
6. push
7. coba edit file yg diexclude
8. <code> git status </code>
9. seharusnya file yg diexclude tsb tidak masuk dalam stage area

```