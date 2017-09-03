### Stashing uncommitted changes

------ To stash uncommitted changes ------
`git stash save -u 'Message'`
    (-u = stash items including untracked files)

------ To list stashed items: ------
`git stash list`

------ To show what changes has been stashed: ------
`git stash show stash@{0}`

------ To apply stashed items: ------
`git stash apply stash@{1}`

------ Only stash unstaged items: ------
`git stash save --keep-index`

------ Interactive stashing (choose what to stash): ------
`git stash --patch`

------ Remove the latest stash: ------
`git stash drop`

------ Remove a specific stash: ------
`git stash drop stash@{0}`

------ Remove a single stash and apply it on top of current working tree: ------
`git stash pop`
