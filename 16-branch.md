
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
