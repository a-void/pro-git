### Branching scenarios

##### Creating a remote branch based on another remote branch

```
git checkout -b new_branch origin/old_branch      // creates a local 'new_branch' based on remote 'old_branch'
--- OR ---
git checkout old_branch                           // creates a local 'old_branch' based on remote 'old_branch'
git push -u origin new_branch                     // pushes the newly created local 'new_branch' to remote origin and sets up to track it

```
----------------------------------------------------------------------------------------------
##### Merging remote branch into local:

Currently working on local branch 'feature-1' that was branched off from remote 'dev' branch.
Made some commits to local branch 'feature-1'.
Now 'dev' branch has been updated.
Need to pull latest 'dev' updates onto local 'feature-1' branch.

```
git checkout feature_1  // make sure youre in the local 'feature_1' branch
git fetch               // fetch the updates

--- SOLUTION 1 ---
git merge ogirin/dev    // takes new commits from 'dev' and adds them on top of 'feature_1'

--- SOLUTION 2 ---
git rebase origin/dev   // takes new commits from 'dev' and inserts them UNDER 'feature_1'
                        // More precisely, it modifies the history of 'feature_1' such that it is based on the tip of 'dev', with any changes you made on top of that.
```

So why would you want to use 'git pull --rebase' rather than 'git pull'? Heres a simple example:

You start working on a new feature.
By the time youre ready to push your changes, several commits have been pushed by other developers.
If you 'git pull', your changes will be buried by the new commits.
If you 'git pull --rebase' instead, git will fast forward your master to upstreams, then apply your changes on top.
----------------------------------------------------------------------------------------------
##### Renaming remote branch:

```
git checkout -b new_branch origin/old_branch      // creates a local 'new_branch' based on remote 'old_branch'
git push -u origin new_branch                     // pushes the local 'new_branch' to remote (-u sets up tracking)
git push -d origin old_branch                     // deletes 'old_branch' from remote origin

```
----------------------------------------------------------------------------------------------
##### Push local branch changes to specific remote branch (dev):

```
git checkout -b new_branch origin/dev             // creates a local 'new_branch' based on remote 'dev'
git commit -m 'Commit msg'                        // commit local changes on 'new_branch'
git push origin dev                               // pushes local commits onto remote 'dev' branch

```

----------------------------------------------------------------------------------------------
##### Merge changes made on local branch into specific remote branch (dev):

```
git checkout -b fund_data origin/dev              // created 'fund_data' branch based on remote 'dev'
  --> do some work on fund_data branch
  --> commit all changes on fund_data
git checkout dev                                  // switch into local 'dev' branch based on remote 'dev'
git fetch                                         // fetch latest changes from remote 'dev'
git merge origin/dev                              // merge latest changes from remote 'dev' into local 'dev'
git merge fund_data                               // merges content in 'fund_data' into local 'dev'
git push origin dev                               // pushes local 'dev' into remote 'dev'

```
----------------------------------------------------------------------------------------------
##### Delete branches

```
git push -d origin old_branch                     // deletes 'old_branch' from remote origin (checks whethers 100% merged)
git push -D origin old_branch                     // force delete 'old_branch' from origin (deletes even if not merged)

git branch -d old_branch                          // deletes 'old_branch' locally

```
----------------------------------------------------------------------------------------------
