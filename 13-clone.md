# Clone 
``` bash
git clone "url://....""
```

## Option 1
Option 1
With this, you fetch all the branches in the repository, checkout to the one you specified, and the specific branch becomes the configured local branch for git push and git pull . 

But you still fetched all files from each branch.
``` bash
git clone "url://...."" --branch BRANCH_NAME
git clone "url://...."" -b BRANCH_NAME
```

## Option 2
This performs the same action as option one, except that the --single-branch option was introduced in Git version 1.7.10 and later. It allows you to only fetch files from the specified branch without fetching other branches.

``` bash
git clone "url://...."" --branch BRANCH_NAME --single-branch
git clone "url://...."" -b BRANCH_NAME --single-branch

# To check, show all detail info for origin: url, branches etc
git remote show origin
```