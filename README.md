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

### revert changes
- reset branch to the remote
```
git reset --hard origin/<branch_name>
```
- revert merge(The -m followed by the 1 indicates that we want to keep the parent side of the merge )
```
git revert -m 1 <merge_hash>
```
### diff
- diff on file between differen commits
```
git diff 6c7d12b 8d22db7 README.md
```

### merging
- squash merge
```
(master) git merge --squash develop
```
- not fast-forward merge with without auto commit
```
(master) git merge --no-ff --no-commit develop
```
- squash all commits on branch develop
```
(develop) git rebase -i HEAD~2 (2=no of commits to squash)
```
  pick commits to squash or pick -> ^X -> edit comments -> ^X
```
(develop) git push develop --force
```
- pick all changes from develop branch and override the curent one(master)
```
(master) git merge develop -Xtheirs
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
### tagging
- create local tag
```
git tag v1.1.0
```
- create remote tag
```
git push origin v1.1.0
```
- remove remote tag 
```
git push --delete origin v1.1.0
```
- remove local tag
```
git tag -d v1.1.0
```
### submodules
```
git clone <repo> --recursive
cd <repo_dir>
git pull --recurse-submodules
```

### other

check changes between branches ( useful to see which changes haven't been cherrypicked yet)
```
(develop) git cherry master
```
```
(develop) git log --left-right --graph --cherry-pick --oneline develop...master
```

change commit message 
```
git commit --amend -m "New commit message"
```
```
git push origin branch_name -f
```

undo things
https://github.com/blog/2019-how-to-undo-almost-anything-with-git

