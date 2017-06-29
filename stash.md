### Stashing uncommitted changes

**To stash:**  
`git stash`  
`git stash save`  

**To list stashed items:**  
`git stash list`

**To apply stashed items:**  
`git stash apply`  
`git stash apply stash@{1}`  

**Only stash unstaged items:**  
`git stash --keep-index`  
`git stash save --keep-index`  

**Stash all items including untracked files:**  
`git stash -u`  
`git stash --include-untracked`  

**Interactive stashing (choose what to stash):**  
`git stash --patch`  
