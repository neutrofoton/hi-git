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