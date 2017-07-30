### Branching scenarios

##### Creating a remote branch based on another remote branch

```
git checkout -b new_branch origin/old_branch      // creates a local new_branch based on remote old_branch
git push -u origin new_branch                     // pushes the newly created local new_branch to remote origin and sets up to track it

```
----------------------------------------------------------------------------------------------
##### Merging remote branch into local:

Currently working on local branch `feature_1` that was branched off from remote `dev` branch.
Made some commits to local branch `feature_1`.
Now `dev` branch has been updated.
Need to pull latest `dev` updates onto local `feature_1` branch.

```
git checkout feature_1  // make sure youre in the local `feature_1` branch
git fetch origin/dev    // fetch the updates from the remote `dev` branch

--- SOLUTION 1 ---
git merge ogirin/dev    // takes new commits from `dev` and adds them on top of `feature_1`

--- SOLUTION 2 ---
git rebase origin/dev   // takes new commits from `dev` and inserts them UNDER `feature_1`
                        // More precisely, it modifies the history of `feature_1` such that it is based on the tip of `dev`, with any changes you made on top of that.
```

So why would you want to use `git pull --rebase` rather than `git pull`? Heres a simple example:

You start working on a new feature.
By the time youre ready to push your changes, several commits have been pushed by other developers.
If you `git pull`, your changes will be buried by the new commits.
If you `git pull --rebase` instead, git will fast forward your master to upstreams, then apply your changes on top.
----------------------------------------------------------------------------------------------
##### Renaming remote branch:

```
git checkout -b new_branch origin/old_branch      // creates a local new_branch based on remote old_branch
git push -u origin new_branch                     // pushes the local new_branch to remote (-u sets up tracking)
git push --delete origin old_branch               // deletes old_branch from remote origin

```
