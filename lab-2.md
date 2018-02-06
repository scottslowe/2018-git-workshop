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
