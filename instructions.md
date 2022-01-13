# Lab: Git and GitHub for Teams in MSCI 342

The objective of this lab is for you and your team to work together to learn the basics of the MSCI 342 workflow of developing software with git and GitHub.  

In MSCI 342, we use the GitHub flow model with a shared repository.  We do not use "fork and pull". Teams are required to use this workflow.  You may have used git and GitHub at a co-op job in a different way, but for MSCI 342, you must follow our workflow.  

## GitHub's "master" is now "main"

The default branch (the first branch created) in git was [historically named "master"](https://sfconservancy.org/news/2020/jun/23/gitbranchname/).  In the Fall of 2020, [GitHub switched to using "main" as the default branch name.](https://github.com/github/renaming)  You will find lots of existing literature and videos using "master" and should simply think "oh yeah, that's now main".  If you use git (not GitHub) to create a git repository, you are likely to still have the default branch be named "master".  I recommend always creating repositories in GitHub with a README.md file and then cloning them to your local workspace so that your default branch is "main".  

## Notes to students with significant prior experience with git

### What I want from git experienced students

Some students have lots of experience with git and GitHub.  I want these students to help explain what I may fail to communicate well in this lab or in lecture.  Please be a teacher-leader and help your teammates learn git.  Since everyone will be using git and GitHub to contribute to the project, it is important everyone learn it to maximize team output.  

### What I don't want from git experienced students 

Do not encourage your teammates to deviate from the required workflow.  

I do not want you to create complex release branches or even a development branch.  We only use branches for the life of developing the feature or code that needs to be added to main.  After we complete a pull request, we will delete the branch.  The main branch represents the code that ships to the client, and all other branches are ephemeral and live for only a couple of days.

We don't use rebasing in MSCI 342. Do not introduce rebasing to your team.  Because all of a team's branches may be used by someone else on the team, do not rebase.  

## Prerequisites

1. You need to have accepted your invitation to the [UWaterlooMSCI342](https://github.com/UWaterlooMSCI342) GitHub organization.  Contact your team's TA immediately if you cannot find your invite and get yourself into the organization and your team.

2. At a minimum you've read the [Git Handbook](https://guides.github.com/introduction/git-handbook/) and [Understanding the GitHub flow](https://guides.github.com/introduction/flow/).  We use a shared repository in MSCI 342.  We do not use fork and pull.

3. As you progress through the MGTE program, we expect that you will take increasing responsibility to do the reading and learning necessary to succeed in a course beyond the material presented in lecture.  Often lectures can only introduce or help explain the big picture.  Outside of lecture is where you learn the details.  It is recommended that you do more than just read  the minimum materials above.  A good place to start are the following videos, which are very good (better than most books).  Note that the that last video describes "fork and pull" rather than a shared repository approach, but otherwise it is very applicable and helpful to understand remotes such as GitHub.  I wish these videos had existed when I first started learning git.

    - [Introduction to Git](https://youtu.be/uR6G2v_WsRA)
	- [Branching and Merging](https://youtu.be/FyAAIHHClqI)
	- [Remotes and GitHub](https://youtu.be/Gg4bLk8cGNo)

4. Make sure you give Codio permission to the UWaterlooMSC342 organization:

	- In GitHub, click on your name and then select "settings".
	- Select "Applications".
	- Click on the "Authorized OAuth Apps" tab.
	- Click on the blue "Codio" logo.
	- Grant Codio permission to the UWaterlooMSC342 organization.


### Create a shared repository 

Repository creation is done by 1 team member only.  Everyone on the team should follow along in person or via "share screen" if working remotely as a team.  Work with each other, and help each other.

1. Go to https://github.com/UWaterlooMSCI342

1. Be sure you are on the Repositories tab.

1. Click on the green "New" button.

    - Ignore the stuff about "Repository template".

    - Name your repository `W22-gitlab-team-NNN` where you replace NNN with your team number, e.g. `W22-gitlab-team-1`.

    - Leave the description blank.

    - Keep the repository private.  ALL repositories in MSCI 342 should be private.

    - Click the option to "Add a README file" .   Do not select any other options.

     - Click "Create repository"

1. Click on "Settings" (to the right of "Insights")

1. Now we want to give everyone on the team admin access to the repo.  

	- Click on "Manage access"

	- Click on green button "Add teams"

	- Search for your team and select it.

	- Give your team "Admin" access. This gives everyone on the team Admin control of the repo, which is needed to be able to deploy to Heroku as well as control other settings.

	- Then click the big green button to add your team to the repo.

1. Next, we want to protect the master branch from people pushing changes onto it without review from the team.  Trust me: we want this to help us develop a good process with source control and GitHub.  You **must** setup your team's project repo with the `main` branch protected.

    - Click on "Branches"

    - Under "Branch protection rules", click "Add rule"

    - Type in "main" for the "Branch name pattern"

    - Select: "Require pull requests before merging".

    - Select: "Include Administrators". 

    - Double check that you've done this correctly.  Then **click the green "Create" button** at the bottom of the page.  The button may be off the page and not visible without scrolling.

### Save the above instructions

**The above instructions are also what you will do to create the repository for your team project except that you'll name the team's project repository W22-team-NNN.**
### Protected "main" branch

Now, because the `main` branch is protected, it is VERY IMPORTANT that you **NEVER commit anything to the main branch**.  You MUST always first create a branch or switch to a branch before you do any work in your repository.  If you commit to the `main` branch, you will put your local repository into a state that is tricky to fix.  
### Clone the repo

Each teammate should, in their own Codio terminal, clone the repo:

```
git clone git@github.com:UWaterlooMSCI342/W22-gitlab-team-NNN.git
```

where you make sure to replace `NNN` with your team number.  You should now find a directory named W22-gitlab-team-NNN with the README.md file in it.

### Edit the README.md file

The README.md file is written in a format called Markdown. Markdown makes created formatted files easy.  You can think of markdown as a shorthand for HTML.  I find that this [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) is all I need for 99% of what I want to do in markdown.

One person on the team should do the following work and everyone else on the team should follow along (either in person, or via a "share screen" if working remotely)

1. Be sure you are in the W22-gitlab-team-NNN directory: 
    ```
    cd W22-gitlab-team-NNN
    ```
1. Create a branch to work on:
    ```
	git branch adding-names
	```
	This makes a "copy" of the `main` branch where you go to work on the project.
1. To "go to the branch", you have to `checkout` the branch:
    ```
	git checkout adding-names
	```
1. To make sure that you are now on the branch, do:
   ```
   git status
   ```
   and be sure it tells you that you are on branch `adding-names`.  You should see `On branch adding-names`.  Remember that if in doubt, `git status` is the command you should run.  You need to always be aware of what branch you are working on.  Before you do any other git command that could change the repo, you should do `git status` to be sure you are in the state you expect.

1. Using the Codio file tree, click on `README.md`.  Codio tries to be real helpful, and it display all markdown files in preview mode.  To actually edit the file, you need to click on the little pencil icon in the upper right of the file's window.  (If you want to directly edit the file in the terminal, you could do `nano README.md` to use the nano editor.  Or, if you know vim, you don't need my help.)

1. Edit the README.md file to look like the following, but add all of your teammates actual names and actual team number:
    ```
	# Team NNN

	* Beth
	* Ahmed
	* Mark
	* Harish
	* Alexandra
	* Sue
	```
	To check out how it looks, you can click the small icon with a page corner turned (mouseover says "preview").  When done, do File->Save all files in Codio.  Codio seems to automatically save files, but it doesn't hurt to be sure it has.

1. Close the `README.md` tab so that you don't accidentally change the file.

1. Run `git status` to see that git knows you've modified the file.  

1. Add the file to the staging area:
    ```
	git add README.md
	```

1. Commit the staging area:
    ```
	git commit -m "Added team names to README`
	```

1. Now, your local repository has this branch, but GitHub does not.  We want to send the branch and all the changes to GitHub.  To do that, we use `git push`.  Do:
    ```
	git push
	```
	and git will tell you that you cannot do that, because for this branch, it is not connected to a remote repo.  This is the error message that I get:
	```
	fatal: The current branch adding-names has no upstream branch.
    To push the current branch and set the remote as upstream, use

    git push --set-upstream origin adding-names

	```
    So, that is what we really need to do when we first want to push a branch.  All subsequent pushes of a branch only require `git push`.  Do it:
	```
    git push --set-upstream origin adding-names
	```
	The name `origin` is the default name for a remote, and since we cloned our repo from GitHub, `origin` is the GitHub shared repo. 

	If you ever want to see all the branches in your local repo, you can do `git branch --all` and it will list them.  It will place a `*` next to your current working branch.  But, perhaps more useful is this cool command from David Mahler's videos:
	```
	git log --all --decorate --oneline --graph
	```
	Go ahead and try it out.  This shows the commit graph for our repo.  If you want to understand the output, please watch [the video](https://youtu.be/FyAAIHHClqI).  Mahler suggests to make an alias to save time typing:
	```
	alias graph="git log --all --decorate --oneline --graph"
	```
	and then you can just type `graph`. 

1. You can repeatedly commit and push code to GitHub on your branch.  This is the same as you did in MSCI 245.
1. Go to https://github.com/UWaterlooMSCI342 and either find your repo or click on "Teams" and your team name and then "Repositories" to find your repo.  Click on your repo name.

1. Notice that the README.md file, does not show your changes.  This is because you are viewing the main branch, and your changes are on the `adding-names` branch.

1. You will see a dropdown button that has a mini commit graph and the name "main" on it.  This button lets you select the branch you want to view in GitHub.  Click the button and select "adding-names".  You should see the README.md change to match the work you committed and pushed. 

1. There should be a message that says "This branch is 1 commit ahead, 1 commit behind main."  To the right of that message are links for "Pull Request" and "Compare".  Click on "Compare".

1. Look down the page (scroll as needed), and you can see the differences between the main branch and the adding-names branch.  If it looks like you expect, click the big green button "Create pull request"

1. For now, you don't need to add a comment, but for the project, we'll give you guidance on how to write a good pull request (PR).  Click again "Create pull request".

1. Your pull request needs to be reviewed by another team member before your PR can be merged with main.  I recommend that you click the little "gear" icon next to "reviewers" and select each of your teammates for a review.  Each of them will get an email telling them that you'd like a review of your PR.  
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
### Review

Okay, we've gone through a lot.  A quick review:

To do any new work, you need to create a new branch and switch to it.  When you name your branch, name it to describe the purpose of the work you are doing.  
```
git branch name-of-work
git checkout name-of-work
```
Do not forget the checkout!  If you want a shortcut to create and checkout a branch in one command, you do:
```
git checkout -b name-of-work
```
The `git checkout name-of-work` is how you switch to a branch named `name-of-work`.  

Before you switch from a branch that you are working on, you should commit all work.

When you want GitHub to have a copy of your branch, you do `git push`.  

Anyone else on the team can then do:

```
git fetch
```

to obtain your branch.  To switch to it, they would use `git checkout name-of-work`.  If you are both working the branch, or need to obtain the latest changes from GitHub, you run

```
git pull
```

and this fetches and merges the new material in the branch.

### Keeping up to date with a changing `main` branch

Your local repo does not automatically sync with GitHub.  It only updates when you tell it to.  At least once a day you should:

1. If you are working on a branch, commit your work.

1. `git checkout main` to switch to the main branch

1. `git pull` to get the latest changes from GitHub and merge them into your copy of the `main` branch.  Think of this as updating your local copy of `main`. 

1. Now, switch back to your working branch with `git checkout my-working-branch-name`.

1. To get the new changes from the `main` branch into your branch, you need to merge them with `git merge main`.  If you have any conflicts, you will need to resolve them. 

You **must** also do this syncing before you `push` and create a pull request.  You want your branch up to date with the `main` branch before you declare to the team that your code is working and ready for merging with `main`.  
#### Resolving conflicts

If you run `git merge main` and there are conflicts, you'll get a message from git telling you which files are in conflict and that "Automatic merge failed; fix conflicts and then commit the result."

To see the files that need work, do `git status`.

Then open each of these files.  You will see one or more sections like:

```
<<<<<<< HEAD
This is code you wrote in your branch.
=======
This is code that is on the main branch.
>>>>>>> main
```

From `<<<<<<< HEAD` to `=======` is what you have in your working branch.  The part from `=======` to `>>>>>>> main` is from the main branch.  It has the changes that you just pulled in.

You need to decide what the file should really look like.  Either take your version, or the new version, or go and talk with your team to decide what to do.  

Fix up the file to be correct.  (You will also remove the `<<<<<<< HEAD` and `=======` and `>>>>>>> main` text, for they should not be in the file if you've made it be correct working code.)

Once you've made your changes, `git add` the fixed file, and then `git commit` the file.  You will have resolved the conflicts and finished the merge.
### Everyone gets to practice

Alright, now it is time for everyone on the team (including the people who have so far done all the work) to do the following:

1. Run `git pull` to update your `main` branch.

1. Create a new branch: `git branch firstName` where `firstName` is your name.  This way each person gets their own branch without conflict.

1. Switch to the branch with `git checkout firstName`

1. Create a new file named `firstName.md` where you replace `firstName` with your name.

1. Inside this file, create a heading with a `#` character and then type your first and last names, for example `# Mark Smucker`.

1. Inside this file, create a list of things that you like. For example:
    ```
	# Mark Smucker

	Likes:

	- Cherry pie.
	- Bicycling.
	- Movies.
	```

1. Edit `README.md` and link your name to your file.  For example:
	```
	# Team NNN Members

	* Beth
	* Ahmed
	* [Mark](Mark.md)
	* Harish
	* Alexandra
	* Sue
	```

	Note that file names are case sensitive.  Be sure to use the same case in your link as you did in naming the file.

	Unfortunately, you cannot test that the link works locally on Codio, but you need to git the markdown files to GitHub to check.

1. Add and commit the changes to git.  Push them to GitHub.

1. Go to GitHub and view your branch.

1. Click on your name in the README.md file.  It should take you to the file in GitHub.  

1. If everything is good, do the pull request.  Have a teammate who has not approved any other requests yet, review and approve.  GitHub may tell you that there is a conflict and it needs to be resolved.  This is because you and other teammates were editing README.md at the same time.  Not a problem!  To fix:

	- Go back to your local repo on Codio.

	- `git checkout main`

	- `git pull`

	- `git checkout firstName`

	- `git merge main`

	- Resolve the conflict in README.md.  

	- `git add README.md`

	- `git commit -m "fixed conflict"`

	- `git push`

	- Go back to GitHub and see if you can merge the PR now.

## What to turn in

Each person will be marked based on:

1. Their information appearing correctly in GitHub.

1. The submission of a PR for their changes.

1. They reviewed and approved at least one other teammates' PR.  

1. All branches were deleted once merged.

The repo in GitHub should remain until the work has been graded.














