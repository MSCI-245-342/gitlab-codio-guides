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

