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

