### Branching scenarios

##### Merging remote branch into local:

Currently working on local branch `feature_1` that was branched off from remote `dev` branch.
Made some commits to local branch `feature_1`.
Now `dev` branch has been updated.
Need to pull latest `dev` updates onto local `feature_1` branch.

```
git checkout feature_1  // make sure you're in the local `feature_1` branch
git fetch origin/dev    // fetch the updates from the remote `dev` branch

--- SOLUTION 1 ---
git merge ogirin/dev    
                        // takes new commits from `dev` and adds them on top of `feature_1`

--- SOLUTION 1 ---
git rebase origin/dev   
                        // takes new commits from `dev` and inserts them UNDER `feature_1`
                        // More precisely, it modifies the history of `feature_1` such that it is based on the tip of `dev`, with any changes you made on top of that.
```

So why would you want to use `git pull --rebase` rather than `git pull`? Here's a simple example:

You start working on a new feature.
By the time you're ready to push your changes, several commits have been pushed by other developers.
If you `git pull`, your changes will be buried by the new commits.
If you `git pull --rebase` instead, git will fast forward your master to upstream's, then apply your changes on top.
