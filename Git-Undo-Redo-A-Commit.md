#### When to UNDO/REDO?

You would typically want to UNDO/REDO when you commit some changes to git, and realize that the changes need to be removed/reverted. This very common in scenarios for example, when you did a temporary change to some files, and forgot to revert them, then proceeded to adding them to commit accidentally.

#### The UNDO/REDO workflow:

Assuming you did some changes and made commits like: <br>
`git commit -m "Commit 1 - Some changes to the code"`<br>
`git commit -m "Commit 2 - Some MORE changes to the code"`

Step 1 (UNDO-ing): Revert back the last commit <br>
`git reset --soft HEAD~ ` <br>
Step 2: *Do the changes.* <br>
Step 3: Add your files to the staging area<br>
`git add <filenames or paths>` or `git add --all` <br>
Step 4 (REDO-ing): Do the commit. <br>
`git commit -c ORIG_HEAD` or `git commit -C ORIG_HEAD`

##### How does this work?

Now that you know the flow lets understand how this works behind the scenes.

1. `Step 1` resets the last commit i.e. `"Commit 2 - Some MORE..."` back to the `"Commit 1 - Some..."` commit.
2. In `Step 2`, you do changes you deem fit to the files.
3. In `Step 3`, you add the changed files to the staging area either selectively with `git add <filenames>` or all files with `git add --all`.
4. In the final step you commit the changes in the staging area. 

Note: you can either use `-c` or `-C`. The small `-c` will open an editor for modifying the commit message, in this case it will be `Commit 2 - Some MORE...`. You can edit the commit message as you want.

Or alternatively you can use caps `-C`, where git will skip the editor window, and reuse the *LAST* commit message which again in this case is `Commit 2 - Some MORE...`.

Re-using the "Same" commit message is also known as redoing/recommiting.

#### Some More tricks:

You can go back any number of commits by using `git reset --soft HEAD~n` where you want to undo last `n` commits.

###### *Attribution: This article is based on a Stack Overflow question [here](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit/927386#927386).*
