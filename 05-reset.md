# Reset 
``` bash
git reset --hard HEAD~1 # reset working copy back to HEAD and remove all changes and undo multiple changes.

git reset --soft HEAD~1 # reset HEAD state to HEAD~1
                        #  and put all changes previous HEAD to staging area of new HEAD (HEAD~1)


git reset # can be used to undo command : $ git add .
```

```bash
# undo git commit
git reset --soft HEAD^

# undo git add
git reset 
```

1. <code>reset --soft HEAD^ </code>, undoes <code>git commit</code> and brings you back to your git stage post- <code>git add</code>.

2. <code>reset</code> , undoes <code>git add </code>, bringing you back to your git status before <code>git add </code>