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
