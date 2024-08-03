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