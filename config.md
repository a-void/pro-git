## Config

##### Updating username/author

```
git config user.name 'Art Vitiuk'
git config user.email 'art@art.com'

```

##### Updating commits done by old author

```
git log
git rebase -i 8fd80663b3e0f32f4baf88638a5888899d71ddf0^

--- select previous commits to _edit_ ---

git commit --amend --reset-author
git rebase --continue

git commit --amend --reset-author
git rebase --continue

git push

```
