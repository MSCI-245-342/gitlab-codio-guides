### Create a shared repository 

Repository creation is done by 1 team member only.  Everyone on the team should follow along in person or via "share screen" if working remotely as a team.  Work with each other, and help each other.

1. Go to https://github.com/UWaterlooMSCI342

1. Be sure you are on the Repositories tab.

1. Click on the green "New" button.

    - Ignore the stuff about "Repository template".

    - Name your repository `2021-gitlab-team-NNN` where you replace NNN with your team number, e.g. `2021-gitlab-team-1`.

    - Leave the description blank.

    - Keep the repository private.  ALL repositories in MSCI 342 should be private.

    - Click the option to "Add a README file" .   Do not select any other options.

     - Click "Create repository"

1. Click on "Settings" (to the right of "Insights")

1. Now we want to give everyone on the team admin access to the repo.  

	- Click on "Manage access"

	- Click on green button "Invite teams or people"

	- Search for your team and select it.

	- Give your team "Admin" access. This gives everyone on the team Admin control of the repo, which is needed to be able to deploy to Heroku as well as control other settings.

	- Then click the big green button to add your team to the repo.

1. Next, we want to protect the master branch from people pushing changes onto it without review from the team.  Trust me: we want this to help us develop a good process with source control and GitHub.  You **must** setup your team's project repo with the `main` branch protected.

    - Click on "Branches"

    - Under “Branch protection rules”, click "Add rule"

    - Type in "main" for the "Branch name pattern"

    - Select: "Require pull requests before merging".

    - Select: "Include Administrators". 

    - Double check that you've done this correctly.  Then **click the green "Create" button** at the bottom of the page.  The button may be off the page and not visible without scrolling.

### Save the above instructions

**The above instructions are also what you will do to create the repository for your team project except that you'll name the team's project repository 2021-team-NNN.**
