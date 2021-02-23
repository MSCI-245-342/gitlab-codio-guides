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

