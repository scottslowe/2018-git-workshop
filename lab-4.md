# Lab 4: Using remotes

For this lab, we'll be using GitHub to demonstrate how Git remotes work, and how branches play into working with Git remotes.

1. Log into GitHub ([https://github.com](https://github.com)).

2. Locate the repository for this workshop ([https://github.com/lowescott/2018-git-workshop](https://github.com/lowescott/2018-git-workshop)).

3. Click "Fork" to make a copy of the repository into your own GitHub account.

4. Click the "Clone or download" button to get the HTTPS URL for your newly-forked repository.

5. In a directory on your computer, type `git clone <HTTPS URL from previous step>` to clone the forked repository down to your local computer.

6. Change into the directory where Git cloned the repository. Run `git log` to see the history of changes. You'll see the full history of the repository, even from before you cloned it.

7. Run `git remote` to see a list of remotes associated with the repository. Only a single remote, named "origin", should be listed.

8. Run `git remote -v` to get more detailed information on the remotes. You'll see that the "origin" remote has an HTTPS URL (should be the same as the one you got in step 4).

9. Make sure the "master" branch is active, then create a new file, add some content, and commit the new file into the repository. Run `git status` and/or `git log` at the end to ensure you've committed the file to the repository.

10. Now flip over to the browser and refresh the display of your forked repository. Did the change you made show up? Why or why not?

11. In order for the change you made locally to show up in the remote Git repository, you'll need to _push_ the changes. Run `git push origin master` to send the local changes to the "master" branch to the remote named "origin".

12. Repeat step 10. Is the change you made present now?

13. Create and checkout a new branch, add a new file with some content (the content doesn't matter), and commit the file into the new branch. Run `git push origin <branchname>` to push the changes to the "origin" remote in the specified branch.

14. Refresh the browser page where the forked GitHub repository is displayed. You should now see that there are 2 branches, and GitHub is prompting you to create a _pull request._

15. Go ahead and create a pull request, then merge it and delete the branch. You should see the changes made in step #13 reflected in the GitHub display now. Are those changes also reflected in local repository? Why or why not?

16. In order for the changes made on GitHub (via the pull request) to show up locally, you must _pull_ them. Use `git pull origin master` to pull down and merge changes from GitHub into your local "master" branch.

17. Run `git branch`. You'll note that the branch you created is still present, even though it has been deleted from GitHub. Use `git branch -d <branchname>` or `git fetch origin --prune` to remove the extra branch.

18. Is your local repository in sync with the GitHub repository now?

Congratulations! You've completed the hands-on exercises in the Git workshop.
