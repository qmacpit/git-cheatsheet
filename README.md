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
- squash all commits on branch develop
```
(develop) git rebase -i HEAD~2 (2=no of commits to squash)
```
  pick commits to squash or pick -> ^X -> edit comments -> ^X
```
(develop) git push develop --force
```
  

### logs
- pretty log
```
log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

- pretty logs with tags
```
log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset%n' --abbrev-commit --date=relative --branches
```

### info
- files changed in last commit
```
git log -1 --stat
```
- last commit change in a file
```
git diff HEAD^^ _filename_
```
### branches
- remove branch
```
git branch -d the_local_branch
```
- remove remote branch   
```
git push origin :the_remote_branch
```

### other

check changes between branches ( useful to see which changes haven't been cherrypicked yet)
```
(develop) git cherry master
```
```
(develop) git log --left-right --graph --cherry-pick --oneline develop...master
```
