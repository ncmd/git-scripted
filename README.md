# git-scripted

# How to contribute to repo
- Requirements:
  - git

1. Fork this repo
- use github web ui

**NOTE**
- If you have an existing fork, do not delete it.
- Instead, update your fork's master branch
```
git remote add upstream https://github.com/ncmd/git-scripted.giit
git fetch upstream
git checkout master
git merge upstream/master
```

2. Create Ticket in Trello
- Format ISSUEID-00000X

3. Make a new branch before git adding files
```
git checkout -b ISSUEID-00000X
```

4. Get git status and remove any files you do not want 
```
git status
git checkout /path/of/unwanted/file
```

5. Add files 
- All files
```
git add .
```
- Single File
```
git add /path/to/file
```

6. Add any secret files to `.gitignore` file
- this will make git ignore files before publishing

7. Make a commit
```
git commit -m "Updated some file"
```

8. Push commit and branch to your fork's branch
```
export CURRENTGITBRANCH=$(git branch | grep \* | cut -d ' ' -f2)
git push --set-upstream origin $CURRENTGITBRANCH
```

9. Open to your github page pull request
```
export GITHUBUSERNAME="your github name"
open https://github.com/$GITHUBUSERNAME/git-scripted/compare/master...$GITHUBUSERNAME:$CURRENTGITBRANCH?expand=\"
```

10. Merge your branch
- Use ui

11. Sync your clone fork master branch with origin master
```
git checkout master
git pull
```