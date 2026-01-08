# Git

## Configuration command
### For name and email

#### for global 
```
git config --global user.name "my-name"
git config --global user.email "my-email"
```
#### for local 
```
git config user.name "my-email"
git config user.email "my-email"
```

## Branch
make main branch default for all repositories
```
git config --global init.defaultBranch <name>
```
for making branch
```
git branch <branch-name>
```
for changing branch 
```
git checkout <branch-name>
```
for delete branch 
```
git branch -d <branch-name>
```
Remove old branch from GitHub
```
git push origin -d <branch-name>
```
## Add and Commit
### first git add then commit

```
git add <file-name>
or
git add .
```

```
git commit -m "message"
```

### for checking which file is tracked or not
```
git status
```

### for checking all commit and commit id (commit history)
```
git log
```

### for restoring first version  
you need commit hash that you want to checkout 
```
git checkout <hash>
```


### for checking all commit and commit id (commit history)
```
git log
```

### for restoring first version  
you need commit hash that you want to checkout 
```
git checkout <hash>
```
for going back to flow (mean from where you came)
write name of the branch 
```
git checkout main
```
if you change in file and want to go to branch forcefully then
```
git checkout -f main
```

## Push to github
add remote repo to git
```
git remote set-url origin <repo-link>
```
check remote repo
```
git remote -v
```
push to github as main branch.  
-u is for remembering the "origin main"  
origin is pointing to the url that we set  
-u meaning is upstream 
by using -u we can direct use `git pull` and `git push` without specifying branch
```
git push -u origin main
```
- if you change branch in git and then try to push then their will be error  
"fatal: The upstream branch of your current branch does not match"
<br>
- and if we want to push to new branch then specify the branch name while pushing the code, <br>like this:
```
git push origin master
```