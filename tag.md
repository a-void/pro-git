### Tagging


##### Listing tags

```
git tag                           // lists all tags
git tag -l                        // lists all tags
git tag -l 'v1.4*'                // lists all tags that include 'v1.4' in name
                                  // eg:
                                  // v1.4.1
                                  // v1.4.3
                                  // v1.4.5
                                  // v1.4.6

```
----------------------------------------------------------------------------------------------
##### Create an annotated tag

```
git tag -a v1.4                   // tags current HEAD commit with 'v1.4'
git push origin v1.4              // pushes 'v1.4' tag to origin

```
----------------------------------------------------------------------------------------------
##### Tag an old commit

```
git tag -a v1.4 9fceb02           // tags commit '9fceb02' with 'v1.4'
git push origin v1.4              // pushes 'v1.4' tag to origin
--- OR ---
git push origin --tags            // pushes all tags to origin

```
----------------------------------------------------------------------------------------------
##### Checking out tags

```
git checkout v1.4                 // checks out (IN DETACHED HEAD) commit pointing to tag 'v1.4'
                                  // unable to make changes in detached head. follow this:
--- OR ---
git checkout -b new_branch v1.4   // creates "new_branch" with commits up to tag 'v1.4'
                                  // now can make more commits and work from this branch

```
----------------------------------------------------------------------------------------------
##### Deleting tags

```
git tag --delete v1.4             // deletes tag 'v1.4' locally
git push --delete origin v1.4     // deletes tag 'v1.4' from origin

```
----------------------------------------------------------------------------------------------

