1. Git workflow (branching)
1. Other helpful commands.


# Branching
When we are working on a bigger project it is a good practice to **NOT PUSH DIRECTLY TO MAIN/MASTER**. We usually create feature branch and then work on our feature there, once the work is done we ask our colleagues to review change with Pull Request (We will see what that is shortly). Once we are given feedback and solve all the issues - we are allowed to merge our codebase with the one that is in the main branch.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_branch.svg)


# Pull requests

# Additional git commands
## revert
## merge
## rebase
## log
## restore
## reset 
## diff
## tag
## checkout

# Working in a team

## merge conflicts, how to solve them
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
##
