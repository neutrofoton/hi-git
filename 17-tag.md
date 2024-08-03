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
