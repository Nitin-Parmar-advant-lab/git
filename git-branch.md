
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

*Branches in Git are not parent-child linked **after creation***

## Merge and Pull Request
1. clone the repo in system
2. create new branch 
3. make changes 
4. push the code
5. create pull request 
6. if no conflict and PR merged then delete branch

---
### If PR conflict occur
1. pull main branch code
2. change the branch to feature/fix branch
3. merge code from this branch to main one (which is just pulled/cloned)
4. fix the conflict and merge the code 
5. push this new conflict free code 
6. now no PR conflict, after PR merged delete branch 