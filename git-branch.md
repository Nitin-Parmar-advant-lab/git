
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

for creating new branch we have to always move to(checkout) specific branch that we want to inherit code  
Like: main -> master -> test  

but if we want to create direct new branch without checkout
```
git branch <new-branch> <parent-branch>
```

adding extra stuff, adding extra 

*Branches in Git are not parent-child linked **after creation***

this is dc

- this is np
