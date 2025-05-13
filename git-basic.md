# Install git
[Here is a link to the official install page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
Just download the software and run it if you dont want to install via command line.

# Git Basics

- **Remote**: the remote server where our files live
- **Local**: your computer
- **Repo**: code repository 
- `clone`: used the first time you want to copy a repo from remote 
- `branch`: a divergence from the main code base. Usually used for feature development or bug fixes. Branches can come off of branches as we will see later.
- `status`: tells you if you have modified, untracked, or staged files on your local repo and where you stand relative to the remote.
- `pull`: updates your local with what is on the remote 
- `add`: prepares a file for commit
- `commit`: commit lets you track a change to a file, requires a message. These should be brief but informative. 
- `push`: moves your local commits to remote
- `checkout`: switch from one branch to another
- `merge`: join two branches

## get the remote on your computer
In your git terminal/gui navigate to the appropriate folder on local.
`cd my/folder/for/repo`

clone the repo from remote with the proper URL into that folder. 
`git clone HTTPS:some/remote/url`

## Move files or folders into your repo if needed
Your repo folder is now being tracked by git. When you change branches files may disappear or be added based on changes others have made. 

You can add files and folders like normal, just know they will be tracked by git. 
If you are generating files you would like git to ignore, put the path in the `.gitignore` file. 

## Add files to the stage

To add files, use the following command:
`git add some/folder/fileName`

## Commit files
To locally commit the changes you have staged via add, run the following:
`git commit -m "informative but brief message"`

## Push changes to remote

To have you changes show up on the remote: 
`git push`

## Pull changes on remote to local 
`git pull`

## Check your status
`git status`
this lets you know what you have changed on your local branch. 

# Typical git workflow

*Check the branch you are working on*

- `git pull` remote changes on to local, resolve any issues
- make some changes to a file
- `git status` look at your files on local and relationship to remote
- `git add some/folder/file` after making incremental but meaninful changes to file
- `git commit -m "brief and informative message"` those files
- `git push` changes to remote - you may be prompted to pull because of changes on remote. Do that. Deconflict the files if needed. Add and commit the deconflicted files then try your push again. 

**Commiting more frequently is better** 
[cheatsheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)

# Creating Branches

## While on main branch
 `git checkout -b feature/Name`
 
## For first push, set it up stream 
 `git push -u origin feature/Name`

## Ready to merge into main? Make a pull request 
- describe the changes you made and the expected outcome
- connect to a work item/issue
- assign a reviewer
- merge into **main**

## Reviewing code
So you got a pull request, now what?  Checkout the branch, make sure the code runs as expected. Reference the description to
the work item and make sure they align. If the code doesn't run, or the feature doesn't match the work item/description, 
talk with the person who submitted the pull request. Do not approve a PR that does not run. After you approve the pull request,
talk with the author of the code to determine who will merge the code into `dev` and merge with a stand merge (not fast forward).

# Creating a branch of a branch
![branch of branch diagram](https://i.stack.imgur.com/6qEWk.jpg|width)
