# Lab 1: Installing Git

## Linux

Virtually every distribution of Linux includes Git in its repositories. Here are the commands for some of the most common Linux distributions:

For Debian and Ubuntu: `sudo apt install git-all` (this _should_ work for the various Ubuntu derivatives like Linux Mint as well)

For Fedora: `sudo dnf install git-all`

For CentOS: `sudo yum install git-all` (this _should_ also work for RHEL)

## macOS

The easiest way to install Git on macOS is to install it as part of the XCode Command Line Tools:

1. Navigate to [https://developer.apple.com/downloads/more/](https://developer.apple.com/downloads/more/) and log in with your Apple ID. (Membership is free.)

2. Download the latest version of Command Line Tools for your version of macOS (the name of the download usually indicates the macOS version support).

3. Install the downloaded package. Git will be available from your terminal after the installation.

If you'd prefer not to go this route, a Mac OS X binary installer is available at [https://git-scm.com/download/mac](https://git-scm.com/download/mac).

## Windows

Download the installer executable from [https://git-scm.com/download/win](https://git-scm.com/download/win) to install Git on your Windows-based system.

# Lab 2: Creating a Git repository

In this lab you'll create a Git repository, add some content, and commit the new content into the repository.

1. Create a new directory named `git-workshop` that will serve as the _working directory_ for the new Git repository. (It doesn't matter where this directory resides on your computer.)

2. Change into the new directory and enter `git init`.

3. List the contents of the directory (be sure to use `ls -a` if on Linux or macOS, so you'll see all the contents of the directory). You should see a new directory called `.git`. _This is the actual Git repository._

4. Before you commit some changes to the repository, you'll want to configure Git. First, tell Git your name with `git config --global user.name "<Your Name>"` (the quotes are needed).

5. Next, tell Git your email address with `git config --global user.email "<your.address@domain.com>"` (the quotes are needed).

6. Optionally, if you have an editor like Atom or Sublime Text installed, tell Git to use that editor as the default with `git config --global core.editor "/path/to/editor"`. On Linux or macOS, you can use `which subl` or `which atom` to determine the exact location of the command-line utility for Sublime Text or Atom, respectively.

7. Now you're ready to add some content to the repository. Create a new text file named `file-1.txt`. Add some content to the file (the content doesn't really matter).

8. Run `git status`. You should see that the new file you created is listed as an _untracked_ file.

9. Stage the new file by entering `git add file-1.txt`.

10. Run `git status` again and you'll see the file listed as a change to be committed.

11. Run `git commit` to commit the changes. Enter a brief commit message, then save and exit the file in your editor.

12. Run `git status` again and Git will report that the working directory is clean.

13. Run `git log` to see a history of the changes (commits) to the repository. At this point, you'll have only a single commit. The commit will be linked to you (via the information you supplied to Git with the `git config` commands).

14. Create a second file named `file-2.txt`, add some content, and commit the new file into the repository. (Hint: you'll need to use `git add` followed by `git commit`.)

15. Edit the `file-1.txt` file to make some changes to the content (the changes don't matter). Commit the changes to the repository.

That's it---you've created a Git repository, added some files, committed the changes, modified an existing file, and committed that change as well.

# Lab 3: Branching and merging

In this lab, you'll experiment with branches and merging branches. Branches are a key feature of Git, and allow you---among other things---to "safely" test changes before making them a core part of your repository.

1. In the Git repository you created earlier, run `git branch`. You should see only a single branch listed, named "master", with an asterisk next to it. This means it is the active branch.

2. Create a new branch by running `git branch br1`.

3. Verify that the new branch has been created by running `git branch` again. You should see it listed there, but it is not the active branch. To make it active, you'll need to check it out.

4. Check out the new branch with `git checkout br1`. Verify that the "br1" branch is active using `git branch`.

5. Create a new file with some content (the content isn't important) and commit it to the new active branch.

6. Run `git checkout master` to check out the "master" branch. What happened to the file you created?

7. Run `git checkout br1` to check out the "br1" branch again. Is the file you created back again? (The file "disappearing" and "reappearing" is Git updating the working directory to reflect the current active branch. The file created doesn't exist in the "master" branch; therefore, it shouldn't be in the working directory, either.)

8. Check out the "master" branch again.

9. Merge the "br1" branch into "master" by entering `git merge br1`. Does the file you created in the "br1" now show when the "master" branch is active? Use `git log` to see what happened when the branches were merged.

10. Delete the "br1" branch with `git branch -d br1`. Verify that it is gone by running `git branch`.

11. Create another branch, make it active, add and commit some new content, and then delete it _without_ merging it into "master". Can you see how a Git branch could be use to safely "experiment" in a repository?

12. Create a third new branch, make it active, add and commit some new content, and then merge it back into the "master" branch. (Hint: You can use `git checkout -b <branch>` to create a new branch _and_ make it active in a single step.)

Now you have an idea for how to work with branches and merge the changes back into another branch. This information will be very helpful when you start working with Git remotes.

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
