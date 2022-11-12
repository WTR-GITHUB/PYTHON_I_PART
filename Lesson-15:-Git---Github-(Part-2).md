1. Git workflow (branching)
1. Other helpful commands.


# Branching, working within teams
When we are working on a bigger project it is a good practice to **NOT PUSH DIRECTLY TO MAIN/MASTER**. We usually create feature branch and then work on our feature there, once the work is done we ask our colleagues to review change with Pull Request (We will see what that is shortly). Once we are given feedback and solve all the issues - we are allowed to merge our codebase with the one that is in the main branch.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_branch.svg)

command to create branch is:

`git checkout -b <branch_name>`

once you start working on it and do the first push, just do `git push` - git will throw an error but will suggest the correct command on how to set upstream (basically this means that we are mapping the branch from our computer to the one on remote - GitHub, GitLab, bitbucket or whatever you are using)

**Note: git terminal is extremely useful - it gives you suggestions whenever you are doing something wrong. So just keep an eye on terminal messages!**


# Pull requests

As mentioned before once you finish working on the feature and you feel that everything is done - you now should create a Pull Request and inform your colleagues that they now have to review your changes. This way you get feedback from senior colleagues, maybe some guidance how to fix, implement something etc. You can exchange comments in GitHub and other popular version control platforms. Let's go through quick demo of how typical Pull Request looks like.

## merge conflicts, how to solve them
It is quite usual scenario when we are working on branches and let's say you and your colleague change a certain part in the code. And once you are trying to merge those codebases they end up in the merge conflict. As scary as it may sound it actually a typical scenario in everyday life. You just do not need to panic if you see something like that. Just keep inspecting `git status` and look into the files where the changes are appearing. We will now do a quick demo to demonstrate this scenario.

### Hands on part
Follow the steps in order to get the merge conflict

1. split into pairs of 2people
1. create an empty repo
1. invite each other to collaborate
1. create a python file, write couple of functions and commit changes and push.
1. let another party to pull latest changes
1. At this point it is important that both of you do a change to the same file, same function. Try reimplementing it in some other way. But important thing here is that both parties should be trying to do changes in the same place of the file.
1. One party does classic -> add, commit , push. Then another tries doing so as well... And get's a merge conflict
1. communicate with your party which version is the right one and should stay in source code.
1. solve conflict.
1. push changes.


# Additional git commands
## revert
The `git revert` command can be considered an 'undo' type command, however, it is not a traditional undo operation. Instead of removing the commit from the project history, it figures out how to invert the changes introduced by the commit and appends a new commit with the resulting inverse content. This prevents Git from losing history, which is important for the integrity of your revision history and for reliable collaboration.
command:
`git revert <commit_hash>`
reverting multiple commits:


`git revert --no-commit HEAD~3..`

`git commit -m "your message regarding reverting the multiple commits"`


## merge

Merging is Git's way of putting a forked history back together again. The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/merge.svg)
command


`git merge <branch_name>`

## rebase

This moves the entire feature branch to begin on the tip of the main branch, effectively incorporating all of the new commits in main. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch.


`git rebase <branch_name>`
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/rebase.svg)

## log

`git log`

simply allows us to see all the history, commit after commit of what happened.
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_log.jpg)

## restore
if after a commit you have done some changes, but at some point decided that you want to roll back you can do:


`git restore <file_name>`

Not that commited changes cannot be restored like that

## reset 

The `git reset` command is a complex and versatile tool for undoing changes. It has three primary forms of invocation. These forms correspond to command line arguments --soft, --mixed, --hard. The three arguments each correspond to Git's three internal state management mechanism's, The Commit Tree (HEAD), The Staging Index, and The Working Directory.


### Hard

This is the most direct, DANGEROUS, and frequently used option. When passed --hard The Commit History ref pointers are updated to the specified commit. Then, the Staging Index and Working Directory are reset to match that of the specified commit. Any previously pending changes to the Staging Index and the Working Directory gets reset to match the state of the Commit Tree. This means any pending work that was hanging out in the Staging Index and Working Directory will be lost.

### Mixed

This is the default operating mode. The ref pointers are updated. The Staging Index is reset to the state of the specified commit. Any changes that have been undone from the Staging Index are moved to the Working Directory. Let us continue.


### Soft

When the --soft argument is passed, the ref pointers are updated and the reset stops there. The Staging Index and the Working Directory are left untouched. This behavior can be hard to clearly demonstrate. Let's continue with our demo repo and prepare it for a soft reset.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/reset.svg)


## diff

command simply lets us see the differences in a file.
command:
`git diff <file_name>`


## tag

Software as we know it comes in version - Windows 98,2000,7,8,10,11...  Python 2.7, 3.5, 3.6....
Usually naming is as follows:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/tag.png)

command:


`git tag -a v1.4 -m "my version 1.4"`


## checkout


##
