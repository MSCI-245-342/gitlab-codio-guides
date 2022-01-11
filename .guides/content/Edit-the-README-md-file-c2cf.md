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
