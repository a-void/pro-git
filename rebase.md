### Rewriting commit history

`git rebase -i HEAD~3`  
`git rebase -i <commit>`

#### Commands:  
__pick__ = use commit  
__reword__ = use commit, but edit the commit message  
__edit__ = use commit, but stop for amending  
__squash__ = use commit, but meld into previous commit  
__fixup__ = like "squash", but discard this commit's log message  
__exec__ = run command (the rest of the line) using shell  
__drop__ = remove commit  
