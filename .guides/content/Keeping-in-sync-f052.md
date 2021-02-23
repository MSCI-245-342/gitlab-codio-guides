### Keeping up to date with a changing `main` branch

Your local repo does not automatically sync with GitHub.  It only updates when you tell it to.  At least once a day you should:

1. If you are working on a branch, commit your work.

1. `git checkout main` to switch to the main branch

1. `git pull` to get the latest changes from GitHub and merge them into your copy of the `main` branch.  Think of this as updating your local copy of `main`. 

1. Now, switch back to your working branch with `git checkout my-working-branch-name`.

1. To get the new changes from the `main` branch into your branch, you need to merge them with `git merge main`.  If you have any conflicts, you will need to resolve them. 

You **must** also do this syncing before you `push` and create a pull request.  You want your branch up to date with the `main` branch before you declare to the team that your code is working and ready for merging with `main`.  
