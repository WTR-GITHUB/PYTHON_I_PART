gitignore


# Version control systems (git, gitlab, github, bitbucket...)

## What are they?
Put simply it is software that allows you to version your software while working on it with as many people as you wish.

During the course we will be using the most popular Github– [www.github.com](http://www.github.com/). So if you do not have an account yet - register.

Download git bash: [link](https://git-scm.com/downloads)

## What can we achieve with git?

So what does the versioning mean? Well with git we save each an every change everyone is doing and at any given time we can go back into any version of our project, we can revert it into any stage if we want. What is more we can also easily work within a team, you do not have to email chunks of code to each other etc. All the information is beautifully stored on [github](http://www.github.com/) Also modern VSC systems like github or gitlab allow us to also seemlesly deploy, test and do other fantastic things with out codebase.

## setting up git?

open git bash if you are using windows or any terminal on other OS:

1.Setup your name:


`git config --global user.name "name surname"`


2.setup email:


`git config --global user.email full@email.com`


3.Check settings:


`git config --list`


Connecting with ssh key

Open git bash terminal

generate ssh key:

`ssh-keygen -t rsa -b 4096 -C "email@email.com"`


open file id_rsa.pub with any text editor and copy it.

Go to[www.github.com](http://www.github.com/) on top right click on your profile -> settings -> SSH and GPG keys -> New SSH key.

Give the key a name of your choice and paste the key. Click Add SSH Key


## Creating an empty project?
Open [www.github.com](http://www.github.com/) Login and hit Start a project.

Give it a name and click create repository

## How to start working with git?

There are couple of ways to move from here and immediately github will describe opportunities to you if you open your newly created project.

### first scenario

open up terminal:

`git clone repository`

create a file and check what can git say about the file:


`git status`

tell git to start tracking changes within the file:

`git add <filename>`

check status once again
`git status`

What is different this time? Now we need to create a commit, which is simply a point in history of your project showing what was changed and who and when did the change
Let's create it!

`git commit -m "firstcommit"`

check status once again
`git status`

We are ready to push now:

`git push`

congratulations you have now successfully tracked the changes and they are also visible on gitub! Check them out.


## Second scenario

What if you already had a codebase and now suddenly you want to start tracking it? Not a problem

initiate git project in the directory of your choice.

`git init`

now you can check git status once again:

`git status`

to start tracking all files simply:

```
git add .
git commit -m "initial commit"
```

And just like that you now have a repo that is being tracked. But how do we share this with our colleagues? It is not yet connected to GitHub
So for this project create a new GitHubproject. Now all you have to do is to grab origin link which you can find on GitHub project you have created.


`git remote add origin https://github.com/vychiokas/test.git`

now we have to 'push' it to remote:


`git push`



## Start working on existing project

So far we've seen how to create a project but how do we join an already existing one?
it's simple go to projects github page. Click on green button saying **Code** choose the way you want to acquire a copy -> ssh/ hhtp
open up the terminal, go to the place where you want to clone the project and then clone it:

`git clone <link_to_project>`


Now you have acquired a copy of codebase to your computer. Be careful, because it does nto update automatically, to grab latest changes we need to do:

`git pull`

this simply tells git to 'pull' latest changes from remote(github), note that the command is similar to `git push` but does the exact opposite - it updates the local copy of codebase.


Užduotys
Savarankiškai išbandyti visus GIT veiksmus, aprašytus šios pamokos skaidrėse
Sukurti programą, fiksuojant visus kodo pakeitimus GitHub (galima kurti norimą programą arba panaudoti bet kurią iš buvusių paskaitų)