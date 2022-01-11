### Reviewing the Pull Request

Another teammate should review the pull request.  Everyone else on the 
team should watch, or "share screen" to watch and help out.

The steps to review the PR are:

1. Go to the PR and leave a comment saying "Hi, I'm starting the review of your PR."  This lets the person who submitted the PR know, and everyone else on the team know, that you're working on the review.  No need for other people to waste their time doing the same work.  You should go to the "Reviewers" and deselect the other reviewers now.  If you need someone else's opinion later, you can add them back.

1. Read the PR and look at the diff of the code.  To see the diff, click on "Files changed".  If you have questions or comments, make a polite and gentle comment or question about it.  **Watch your language!**  Be gentle.  Most people hate feedback.  Most people feel criticized by any feedback.  Yes, your job is to give feedback and make sure the PR is good and bug free, but your first priority is to keep the team functioning well, and if you hurt the feelings of another teammate, the team will have problems.  One year, we had a PR lead to a team breakup!  I don't ever want to go through that again, and trust me, you don't either.

1. You need to check that the new code works as expected.  To do this, you need to go to your local repo and examine the branch and test it out with any submitted tests or manually test it.  To do this:

	On your own local copy of the repo, you need to commit any work in progress (run a git status, do the appropriate git add, and git commit).  If you are on a working branch, you don't want to mess up your work, so get it committed!

	At this point and time, if you do: 

	```
	git branch --all
	```

	you will not see the `adding-names` branch.  Git does not connect and check in with the remote unless you tell it to.  Indeed, run:

	```
	cat README.md
	```

	to see the contents of the file.  You will not see the changes because you don't have them yet.  To update your view of the remote, you need to run:

	```
	git fetch
	```
	and now, if you do `git branch --all`, you should see a branch called `remotes/origin/adding-names`.

	You need to switch to the adding-names branch:

	```
	git checkout adding-names
	```

	git is smart, and makes you a local branch named `adding-names` and connects it "track" the remote adding-names branch.  Take a look at README.md now:

	```
	cat README.md
	```
	
	The changes have arrived!

	Click on README.md in the file tree and be sure it looks good.  This is your "testing" of the "code".  Close the file tab.

	Often the person who submitted the PR, will need to update their branch before you're willing to approve the PR.  We are going to simulate that here with you asking for a change.

	Go back to GitHub and the Pull Request, and leave a polite comment asking the submitter to please change the heading `# Team NNN` to `# Team NNN Members` because you remember that is what the client wanted.  

	Okay, now the original PR submitter, should go to their local repo.  A quick check with `git status` should show they are still on the `adding-names` branch.  The PR submitter should edit the README.md file as requested and save and close the file.  Then `git add README.md` and `git commit -m "made change requested to modify heading"` and then `git push` to send the changed README.md back to GitHub.

	The team should take a look at the PR now.  You'll see it the new commit has become part of the PR.  Awesome.  The PR submitter should leave a comment "I've changed the heading.  Please check out.  Thanks!"

	The PR reviewer, now needs to get the new README.md to check it out:

	```
	git pull
	```

	Open up README.md and verify the changes.  If it all looks good, go back to GitHub and approve the PR.

	The PR submitter can now merge the changes with the `main` branch!  Go for it!

	Now that the PR has been successfully merged, the `adding-names` branch should be deleted.  Don't litter up the repo with lots of branches.  We will create a new branch for each change or feature that we make.  	GitHub nicely provides a button to "Delete branch".  Click "Delete branch".  

	Both the reviewer and the submitter now need to delete the `adding-names` branch from their local repos.  First, switch back to the `main` branch:

	```
	git checkout main
	```

	Then, to update the main branch with the latest changes and to get rid of deleted remote branches:

	```
	git pull --prune
	```
	
	and then to get rid of the local `adding-names` branch:

	```
	git branch --delete adding-names
	```
