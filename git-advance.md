## Merge and REBASE  
*Always checkout the branch you want to keep updated,
then merge the other branch into it.*  
**`git merge branch2`  
means “Add everything from branch2 into my current branch** 
### Merge
```
git merge <branch>
```
- it merge history, so logs will become messy (Combines histories, Creates a merge commit)
- when check `git log` it will show in timestep order
- but it does not mean it is linear, it is in graph manner {Keeps original commit structure (DAG)}

**For checking graph use this command:**  
`git log --graph --oneline --decorate --all`

### Rebase
```
git rebase  <branch>
```
- it rewrite commit history and Creates new commit hashes
- by that it create Clean, linear history