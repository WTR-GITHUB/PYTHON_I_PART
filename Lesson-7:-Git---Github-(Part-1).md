# Version control systems 

## What are they?
Put it simply - it is software that allows you to version your code while working on it with as many people as you wish.

During the course we will be using the most popular - `GitHub`[www.github.com](http://www.github.com/). 
Download `git bash`: [link](https://git-scm.com/downloads)

## What can we achieve with `git`? 🗺️ 

So what does the versioning mean? At any given time we can save current state of our code base, upload it,  go back to any previous version of our project, we can revert it into any stage and download any changes made by our colleagues. All the information is beautifully stored on [github](http://www.github.com/). Also modern VSC systems like `Github` or `Gitlab` (and others) allow us to also seamlessly deploy, test and do other important things with our codebase.

### Setting up `git` 🧰 

Open git bash if you are using windows or any terminal on other OS:

#### Setup your name:

`git config --global user.name "name surname"`

#### Setup email:

`git config --global user.email full@email.com`

#### Check settings:

`git config --list`


#### Connecting with `ssh` key. 

Open git bash terminal to generate `ssh` key:
`ssh-keygen -t rsa -b 4096 -C "email@email.com"`
Open file `id_rsa.pub` with any text editor and copy it.
Go to[www.github.com](http://www.github.com/) on top right click on your `profile -> settings -> SSH and GPG keys -> New SSH key`.
Give the key a name of your choice and paste the key. Click `Add SSH Key`.


### Creating an empty project? 📃 
Open [www.github.com](http://www.github.com/). Login and hit `Start a project`. Give it a name and click `create repository`.

### How to start working with git?


Open up terminal: `git clone repository`.
Create a file and check what can git say about the file:
`git status`.
Tell git to start tracking changes within the file:
`git add <filename>`.
Check status once again:
`git status`.

What is different this time? Now we need to create a commit, which is simply a **point in history** of your project showing what was changed and who and when did the change. Let's create it:
`git commit -m "first commit"`.

Check status once again:
`git status`.
We are ready to `push` now:
`git push` or better `git push origin <branch_name>`

Congratulations you have now successfully tracked the changes and they are also visible on `Github`! Check them out!


### Second scenario

What if you already had a codebase and now suddenly you want to start tracking it? Not a problem.
Initiate git project in the directory of your choice:
`git init`
Now you can check git status once again:
`git status`

To start tracking all files simply:
```
git add .
git commit -m "initial commit"
```

And just like that you now have a `repository` that is being tracked. But how do we share this with our colleagues?

Now we have to 'push' it to remote:
`git push origin <branch_name>`

### Start working on existing project

So far we've seen how to create a project but how do we join an already existing one.
It's simple go to projects `Github` page. Click on green button saying **Code** choose the way you want to acquire a copy -> `ssh/ hhtp`.
Open up the terminal, go to the place where you want to clone the project and then clone it:
`git clone <link_to_project>`


Now you have acquired a copy of codebase to your computer. Be careful, because is not being updated automatically. To grab the latest changes we need to do:
`git pull` .
This simply tells `git` to `pull` latest changes from remote repository (`Github`). Note that the command is similar to `git push` but does the exact opposite - it updates the local copy of codebase.

###  `.gitignore`

`.gitignore` is a configuration file used in `Git` to specify which files and directories **should be ignored** by the version control system. This is useful for **excluding** files that don't belong in the repository, such as compiled binaries, temporary files, or sensitive information like **passwords**.

The file is named `.gitignore`, and it should be placed in the `root` directory of your `Git` repository.

## Readme.md 📑 

A `README.md` file is a plain text or markdown file commonly found in software projects and repositories. Its primary purpose is to provide essential information about the project, making it easier for users, collaborators, or visitors to understand and use the project. It often serves as the project's documentation, giving an overview of what the project is, how to use it, and other relevant details.


## 🧠 Exercises:
* Create the project that you are going to use for our lessons, add already existing notes in order not to lose them.
* Go once again through todays lecture on your own, if anything is not clear - let us know

## 🌐 Extra reading:

* [README syntax](https://www.markdownguide.org/basic-syntax/)
* [Getting started with git](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)


