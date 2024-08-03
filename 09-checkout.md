
# Checkout 
``` bash
git checkout filename.txt # pull back to HEAD (undo). Can be applied to revert changes

git checkout -- filename # pull back one file (undo)

git checkout abcde file/to/restore # Undo a file to specific commit. Assuming the commit you want is abcde

git checkout "branch_name" # switch working copy to branch "branch_name"

git fetch && git checkout "branch_name" # fetch and switch branch

git checkout tags/{Tag_Name}
```