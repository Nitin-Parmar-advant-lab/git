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
### make main branch default  
```
git config --global init.defaultBranch <name>
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