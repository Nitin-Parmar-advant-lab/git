## Git checkout
```
git checkout <hash>
```

Using this checkout command we only can go back to history and view commits

## Git reset
It allows us to remove the traces of commits in history and gives us the changes we made in those discarded commits  
we can keep those change or discard those  

In simple words: it gives back commit from history or remove commits from history

Two types

1. Soft reset
2. Hard reset

### Soft reset (unstage):  
it moves the specific commit from history to the working directory 

```
git reset --soft <commit-hash>
or
git reset <commit-hash>
```

### Hard reset:
It delete/remove specific commit from history permanently 
```
git reset --hard <commit-hash>
```

### git reflog
Even after reset --hard, Git keeps history in reflog
this command will give list of logs
```
git reflog
```
use this for restore prvious state:
```
git reset --hard "HEAD@{1}"
or
git reset --hard <old-hash>
```

## Git revert 
push code and want back previous commit(undo commit), but also does not want to delete/remove log history 

keep the commits in history 

**Difference: reset delete history and revert does not**

```
git revert <commit-hash>
```
After running this, resolve any conflicts the same way you would during a merge.  
and then do `git add <file-name>`  
and then in last 
```
git revert --continue
```
this will open window, for exiting that window write this: `:qa!`



## Git stash 
if you are working in feature and another bug fix come and don't want to commit currant feature, but still need to save it   
<br>
Temporarily stores your uncommitted changes so you can switch branches or do other work without committing.

```
git stash
```
it will remove all the uncommitted changes and store temporally 

for getting those uncommitted changes back:
first get stash id
```
git stash list
```
then
```
git stash apply "<stash-id>"
```
don't forget to put " ", because if not then powershell understand stash id as a special characters not git command 

and for clearing all stash logs 
```
got stash clear 
```
or can use `git stash pop` for Restore + remove
