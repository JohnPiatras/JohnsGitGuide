# Status and Staging

In this section I am going to look at how to check the status of my repository, what is staging and controlling what is included in a commit.

I've renamed this section "Commit History" to "Status and Staging". In Git BASH I changed to the repository directory and ran the following:
```
git status
```

Here is the output:

![Screen shot of git status output after renaming a file](images/git_status_after_rename.png)

The deleted file and untracked file were actually the same file - I've just renamed it. The change, or deletion, of the original is listed but not staged for a commit. The renamed file is currently untracked.

The above screen shot is also untracked at the moment.

Lets add the file for tracking using:
```
git add 3\ -\ Status\ and\ staging.md
```

But, out of curiosity I'll leave the rest as is, so our status looks like:

![Screen shot of git status output after renaming a file](images/git_status_after_tracking_new_file.png)

So, what happens if we commit and push while our status is like this?

```
git commit -m 'A commit with unstaged changes and untracked files'
git push
```

The files in my Git Hub repository look like this:

![Screen shot of my repository after commit some changes and not others](images/GitHub_repo_screenshot_section3a.png)

The effect of the file rename can be seen - the new file exists. However, it is also there under it's old name as we did not commit that particular change.

Also, if I were to navigate to page 3 - Status and Staging I would see that the images are not showing, as these files are untracked.

My status now looks like:

![Git status showing untracked files and an unstaged deletion](images/git_status_with_untracked_files.png)

I can use `git commit -a` to commit currently unstaged changes (the deletion), but this will not cause the 3 untracked images to be added.

For that I need to do `git add -A`, followed by a commit. After doing this and pushing, my git status is now:

![Screen shot of status of an up to date local repository](images/git_status_A_ok.png)

All is well, and up to date.

## More about Staging

Staging a file add a snapshot of its current state to the staging environment.

Lets try creating a simple text file with some content, staging it then adding more content and commiting it. What actually ends up being committed?

This is my text file:
```
This text was added before staging the file.
```
I've saved it as `staging_text.txt`.

We can then stage this file using `git add staging_text.txt`.

Now, lets make another change to it, I've added another sentence:
```
This text was added before staging the file.
This text was added after staging the file.
```

Now, run `git status`:

![Screenshot showing git status with a staged and unstaged change to the same file](images/git_status_staged_and_unstaged_changes_same_file.png)

So we have a staged change for the new file, and an unstaged modification.

Helpfully, git tells us exactly what we need to do if we want to unstage our staged change to staging_text.txt. This won't modify the file, but it will move it to untracked (as it is new). We might want to do that if we change our mind and want to make further changes.

I'm not going to do this right now, I'm going to 
```
git commit -m 'Commit a partial change to a file'
git push
```

Then, checking on git hub we can see that the file has been pushed with the first sentence, but not the second:

![Screenshot of staging_test.txt on Git Hub](images/staging_text_screenshot_1.png)

This demonstrates that staging a change does indeed snapshot the file at that point in time.

`git status` still show a pending change for this file:

![Screenshot of the unstaged edit to staging_test.txt](images/git_status_unstaged_change.png)

I am going to add, commit and push this change.