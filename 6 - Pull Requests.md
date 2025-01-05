# Pull Requests
Often we will be working as part of a team on a project which means that one person may be working on new feature in a branch, will someone else works on other features or bug fixes in another branch.

Eventually the time will come to merge your branch in to master, but master may have had commits made that your branch does not.

This is were the Pull Requests come in - we want to pull changes into master.

To simulate this I briefly checked out master and added a sentence to the ```staging_test.txt``` file I created earlier which was then commited and pushed to the remote repository. I have since checked out out ```add-page-about-branches``` again to write this page about Pull Requests. This branch does not contain the edit to ```staging_test.txt```.

I am now going commit what I have in this branch, and push that to the repository as well, create a pull request and merge everything back to master while taking screenshots along the way.

![Screenshot of brach and pull request notification on git hub](images/github_pullrequest_01_compare_and_pull_request_option.png)

Looking at the repository on GitHub we can see that this branch has 5 commits not present in master, and that master is 2 commits ahead of this branch.

Click "Compare & pull request" to go to the "Open a pull request" page.

![Screenshot of the open pull request page](images/github_pullrequest_02_open_pull_request.png)

Add a description and click "Create pull request". After doing this you will be taken directly to the new pull request, but lets go to the Pull Request tab instead. This tab shows all open pull requests by default and is where we would go to see pull requests submitted by other contributers.

![Screenshot of the pull request tab, showing our new request](images/github_pullrequest_03_pull_request_tab.png)

Clicking on our pull request will open it:

![Screenshot of the pull request](images/github_pullrequest_04_view_pull_request.png)

Here we can see the commits in this request, and conflicts which need to be resolved. Conflicts may happen if changes (eg bug fixes, or a feature developed independantly of this branch) are made in master that are not present any the branch.

We must resolve the conflicts to continue, so click the button.

![Screenshot of the resolve conflicts page](images/github_pullrequest_05_resolve_conflict_page.png)

The sections marked with ```<<<<<<<``` and the red-lines are conflict markers. The Resolve Conflict button will remain greyed-out until you remove these markers. So, we edit the file in GitHub, removing the conflict markers and keeping the content we want.

![Screenshot after resolving conflicts](images/github_pullrequest_06_conflicts_resolved.png)

Now, click ```Mark as resolved``` followed by ```Commit merge```.

![Screenshot showing the commit merge button](images/github_pullrequest_07_commit_merge.png)

The next page to open is ```Merge pull request```:

![Screenshot of the Merge pull request page](images/github_pullrequest_08_merge_pull_request.png)

Since we have resolved the conflicts, we can now click ```Merge pull request```.

![Screenshot of the confirm merge button](images/github_pullrequest_09_confirm_merge.png)

Then click ```Confirm merge```.

Finally, in our local repository we switch to the master branch and pull down the changes:
```
git checkout master
git pull
```

![Screenshot showing result of pulling down the changes to master](images/github_pullrequest_10_git_pull_master.png)

Which fast forwards our local repository to the most recent commit in master, which is were the merge has happened.