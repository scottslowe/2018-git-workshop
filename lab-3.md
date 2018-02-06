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
