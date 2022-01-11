# Lab: Git and GitHub for Teams in MSCI 342

The objective of this lab is for you and your team to work together to learn the basics of the MSCI 342 workflow of developing software with git and GitHub.  

In MSCI 342, we use the GitHub flow model with a shared repository.  We do not use "fork and pull". Teams are required to use this workflow.  You may have 
used git and GitHub at a co-op job in a different way, but for MSCI 342, you must follow our workflow.  

## GitHub's "master" is now "main"

The default branch (the first branch created) in git 
was [historically named "master"](https://sfconservancy.org/news/2020/jun/23/gitbranchname/).  In the Fall of 2020, [GitHub switched to using "main" as the default branch name.](https://github.com/github/renaming)  You will find lots of existing literature and videos using "master" and should simply think "oh yeah, that's now main".  If you use git (not GitHub) to create a git repository, you are likely to still have the default branch be named "master".  I recommend always creating repositories in GitHub with a README.md file and then cloning them to your local workspace so that your default branch is "main".  

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


