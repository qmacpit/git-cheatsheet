# git-cheatsheet
### reset changes
- all changes     
```
(master) git checkout .
```
- all changes in a file    
```
(master) git checkout _filename_
```

### merging
- squash merge
```
(master) git merge --squash develop
```

### logs
- pretty log
```
log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

### other
check changes between branches ( useful to see which changes haven't been cherrypicked yet)
```
(develop) git cherry master
```
```
(develop) git log --left-right --graph --cherry-pick --oneline develop...master
```
