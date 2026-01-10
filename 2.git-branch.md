
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
*Branches are just pointers to commits.They do NOT “own” code.*

## Merge and Pull Request
*Pull Request = “Can my feature branch be safely merged into main?”*
1. clone the repo in system
2. create new branch 
3. make changes 
4. push the code
5. create pull request 
6. if no conflict and PR merged then delete branch  
(more info in git-advance)  
**`git merge branch2`  
means “Add everything from branch2 into my current branch**  
*Always checkout the branch you want to keep updated,
then merge the other branch into it.*

---
**PR conflict = feature branch is behind main**  
### If PR conflict occur
1. checkout main branch and pull latest code
2. switch to feature/fix branch
3. merge main branch into feature branch (git merge main)
4. fix conflicts and commit
5. push updated feature branch
6. PR becomes conflict-free → merge → delete branch  
(in this case feature/fix branch will have code of main branch also but id doesn't matter because )