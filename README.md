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

### other
check changes between branches ( useful to see which changes haven't been cherrypicked yet)
```
(develop) git cherry master
```
```
(develop) git log --left-right --graph --cherry-pick --oneline develop...master
```
