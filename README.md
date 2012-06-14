git-training
============
Learn to use Git by gitting

The main goal for this is to provide a life-like experience with git that will, hopefully, help you learn how to use this tool from the command-line.  Maybe you'll even brush up on your commandline-fu

##Starters

###Assumptions
1. You know what Git is.
2. You know how to access a terminal
3. You know basic commands to view and edit files(cat, less, vim, subl <-- Personal)

###Download it
Before we download this *repository* we want to make sure that we are in the directory on our computer that we want to store these files that we will be working in. 

I personally have a `~/development` directory.  If you would like one you can run `mkdir ~/development && cd ~/development`

The first thing to do is to download this online(_remote_) repository to your _local_ computer. 

```bash
git clone git@github.com:ktilcu/git-training.git
```

You will some information output on the terminal or you may need to enter your password if you don't have your ssh keys set up. For the moment the output is not entirely pertinent so we will skip it.

###Take a look

Lets take a look and see what that did!

`cd git-training`

`ls -la`

You will see all of the project files and a `.git/` directory. `.git` is where all of the information is stored about this *repository* and the changes being made.

##Test Drive

Let's Jump In.

The first thing we want to do is make a a huge change to the program and then make it available to everyone else.

1. Open the file named `meFirst.txt`. 
2. Remove the `#` to implement the huge change.
3. Save the file and close.

Now that we have worked so hard to update this program we want to store the new version and make sure other people know why we made the change and where to find it.

###Checking

First we must check to ensure that we changed the file and that Git noticed that we changed the file.

`git status`

This command will tell us everything we need to know about the current status of our project.

There are 4 main parts to this message and if there is no data in any of them then it doesn't show that section. The four parts are listed below in order of appearance.

1. Summary information e.g. what *branch* you are on, what *commits* our *local* *repository* has in comparison to the *remote* *repository* we downloaded it from
2. Files *Staged* for *commit* (we won't see this yet)
3. Files *Modified* (we should see the `meFirst.txt` here)
4. *Untracked* files - Files that were added to the  (*working*) directory but that Git has no record of

As long as we see the `meFirst.txt` in the *modified files* section then we can move on.

So, the file is modified, we verified that Git noticed that it was modified and we want to make our changes permanent(kinda).

In order to do so, we must `commit` the change to our *local repository* with an explanation.


###Committing

This is the main part of most SCM (source control something) systems. This process allows us to record the change we made in our *repository* while storing what was there previously. In Git, this process is two-step.

1. *Stage* the file for commit using `git add`
2. *Commit* staged files to our local repository using `git commit`

####Staging

Staging is essentially saying to Git

> Yo Git! I changed this file and I want you to hold onto it while I do some other related work. Ya dig?

In other words:
> This file, the way it is right now, will be part of my next commit

Files **must** be staged before they are committed however, there are ways to stage and commit in one fell swoop.

####Commitment

Using this knowledge we can *commit* our update to our local repository.

```bash
git add meFirst.txt
git commit -m "Implemented Huge New Feature"
```

When we *commit* we get some feedback from Git. Namely,
* The *branch* we committed to (we'll hit that one later)
* The *hash* (address for our changes)
* Summary of changes - how many files, lines, etc

This feedback indicates that git has our changes stored away.

####Surveying

Of course we don't trust Git yet so let's check to see what git stored. 

`git log`

This will show us what *commits* are tracked on this repository.

`git status` 

This will show us the current state of our files (*working directory*) compared to what git is tracking.

You will notice in the `git status` that it says we are 1 *commit* ahead of **origin/master**.

Our *repository* was started by `git clone` this means we did not create it and that the files in it have a history before us. 

**Origin/master** is a pointer to that history.  

####Back To The Roots

**Origin/master** is merely a pointer. It points to a time in our *commit* history that indicates what *commit* the origin repository (e.g. mine on github) is currently on.

In our case it shows that we have 1 more commit in our local repository than mine does on github. This is because you implemented the Huge New Feature in your repository but I haven't in mine.

###YAY!

We have completed stage one. This concludes our orientation to Git and sets you on course to begin committing all kinds of changes. 

If you would like to continue training please refer to `README.md` within the `Stage2` directory.







