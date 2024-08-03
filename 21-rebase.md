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
