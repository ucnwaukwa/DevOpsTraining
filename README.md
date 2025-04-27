# GIT FOR BEGINNERS: DAY 1: 13 APR 2025

# INTRODUCTION
In module, we will be focusing on mastering Git from a theoretical and practical perspective.  Software development requires a lot of efforts in coding, collaboration, testing etc.  It is repetitive and could
work sometimes and other times may not work - sadly so. 

Software development comes with ups and downs: great code, bugs, smell code, emerging requirements, fixes etc. 

Hence, we need some sort of   so we can revert back to when things were working smoothly.  

It's like working with say, Microsoft Word or a graphics software where we save checkpoints 
that can be reverted to in case we have say, a sudden power outage.  

Likewise we need checkpoints in software development too; and this is known as VERSION CONTROL SYSTEM.

Once again, the goal here is not to memorise thousands of commands in Git but to understand the workflow of Git in the making of a software.  What happens behind the scene in Git?

# Definition
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.  
Source: https://git-scm.com

# Our definition: A Version Control System (Git) tracks files for changes   

# REQUIREMENTS 1
1.  Visual Studio code
2.  Git

Note: Git and GitHub are totally different - GitHub is a service provider and Git is a software in itself.  Note that Git is a terminal-first VCS.  We will be deep-diving into GitHub in coming modules.
Also note that there are other services like BitBucket, etc which are online services that can be used to keep store of software changes.

So let's get started with Git...

#  DOWNLOAD AND INSTALL GIT
1.  Download Git from https://git-scm.com
2.  Click on Downloads and it will automatically detect your system OS and you can download Git.
3.  After download, open the file and follow the on-screen promts (Next buttons, Agree button) and it's done!

Note: That the software is installed in our system does NOT mean it is tracking stuff!  

After installation, we now proceed to learning the software...  

Note: Clicking on Documentation > Reference Manuals on https://git-scm opens up loads of info when you click on the git or command buttons.  So how do you find your way around?  This is more of a reference guide!

# FIRST THINGS FIRST

# Demo 1
1.  Create a folder where all our software project files would reside on your laptop, say gitspace
2.  cd to that folder
3.  Ensure you have nothing (files or subdirectories in that folder)
4.  Create 3 directories in this folder (e.g. using mkdir commands, create folders gitspace1, gitspace2 and gitspace3)

# WHAT DOES GIT ACTUALLY DO?
1.  It keeps track of changes made to a file (in our case, source code, scripts etc)
2.  Helps in collaboration from say, 2 to hundreds of developers (remember our initial DevOps intro where we mentioned breaking down silos of dev and operations in the traditional IT environment before DevOps)
3.  Learning approach: Understand the basics, use Git daily, resolve Git problems and you become a master!

# UNDERSTANDING TERMINOLOGIES AROUND GIT
# 1. Repo: 
Short for repository, a repo is a folder containing lots of software files.  This is the combination of having a folder as we created above and tracking the folder - i.e. Folder + Git installed + tracking = Repo
Note: This also introduces us to Git commands which are identifiable by bullets beside them below.

# Demo 2
- git --version (or git -v)
1. Run the above command to confirm git is installed on your device (for Windows, run this on your cmd terminal).
2. To get your folder tracked by Git, you have to initialise Git on that folder.  The tracking of each folder is independent from another.  Using our folders above, initialising Git to track gitspace1 does not mean
it is tracking gitspace2, etc.
3.  You definitely do not want to track everything on your system. So let's get the 'track-worthy' tracked!

# Demo 3
1. Go back to the gitspace folder created in demo 1
2. Use the ls command to list the subfolders gitspace1, gitspace2 & gitspace3
3. Change directory to gitspace1 using the command: cd gitspace1
4. Run the command:
- git status
5. Note: The git status command is a habitual utility command - make it your lifeline ALWAYS
6. Initialise the Git software on this folder, gitspace1, by using the command:
- git init
7. Run the git status command again and notice the difference in output
8. If everything works fine, then gitspace1 is now being tracked by Git!
9. Run the ls -la command again to see if there are any files added to gitspace1 which are hidden!

# Explaining the Git init command further
The git init command is run only once on a folder to enable the changes in that folder to be tracked.  As you proceed with adding, deleting and/or modifying files in your folder, you do NOT need to run git init again.

Behind the hood, git init creates the .git folder (as you might have noticed in Demo 3, item 9 above) which is a hidden folder

# Definition: .git is a hidden folder to keep history of all files and sub-folders in a Git-tracked folder.  Let's take a quick look at this folder...

# Demo 4
1.  Change directory to the gitspace1 folder
2.  Run the command: ls -la
3.  Change directory to .git using the command: cd .git
4.  Notice folders like HEAD, hooks, refs, config etc.  These folders would increase as we add more files to the tracked folder, gitspace1.
5.  You will NEVER need to manually edit or change these folders.  Editing these folders can mess up the Git system! However, we only need to know they exist


# 2. Commit: 
The commit statement can be likened to creating checkpoints.  The process is as below

# WRITE ---> ADD ---> COMMIT

A couple of commands preceed the commit command and we need to understand these using a white-board session...

# Whiteboard 1
1. git init (Note that we have already done this before.  This creates what we call a WORKING DIRECTORY)
2. Create files using: touch file1 and file2 in the gitspace1 directory
3. Run the command:
- git add file1 file2 or git add .
- git status
4.  This gets the new files (file1 and file2) into a STAGING AREA. Note that files in the staging area are not yet committed.  Remember that committed means that the checkpoint has not been made but is like saying: 'I'm ready to commit the changes'
5. Run the command:
- git commit
6. Immediately the git commit is run, the changes are committed to the repo
7. The last command would be:
- git push
8. This command sends the changes  to say, a remote Github service

Before we push to a remote Github service, let's understand: the working directory, the staging area and the repo in detail using a demo.


# Demo 5
1. Use the pwd command to identify your present working directory
2. Change directory to gitspace1 (our working directory - i.e. the directory where we initialised git)
3. Run the git status command.  Remember: The git status command should be a habit for you! You ALWAYS need this to check the status of your directory
4. You would ALWAYS be on one OR another branch: master, main, checkout, feature, etc
5. Open the gitspace1 folder on Visual Studio to enable us work on the folder
6. Assignment: Install GitLens on VS Code to be able to show graphically where you're at per time.
7. Go back to the terminal and create a couple of files e.g. using the following command: touch gittest1.txt gittest2.txt
8. Confirm them visually on VScode
9. Run the git status and notice the output especially the message 'untracked files...'
10. Next, use the git add command to add gittest1.txt to be tracked: git add gittest1.txt
11. Run the git status command and notice the changes, especially the message 'changes to be committed...'
12. Note that you are now on the staging area
13. Definition: Staging area is an intermediate zone before you make any commit.  It's like a preview before you send your work to a printer to print!  It helps you to determine if you actually want to commit the changes
14. Next, use the git commit command to commit.  However, let's look at the git commit command in detail...

The commit command always needs a message as to why you are making the commit.  And that message can be added using the -m option thus:

- git commit -m "add gittest1 file"

15. We are now in the repo stage, so we run the git status command to see that gittest1.txt has gone into the repo; yet, leaving the gittest2.txt command as untracked.

In the next class, we will go through the process with gittest2 and expose the importance of GitLens and some possible errors you may have!


# GIT FOR BEGINNERS: DAY 2: 19 APR 2025

# REFRESHER
The 'Write > Add > Commit' practice above is a utility process for most developers.  Hence, we need to practice this as often as possible.

Using day 1 examples above, please go ahead with Demo 6 below

# Demo 6
1. Use the command:

- git status

... to establish that gittest2 file is yet to be added to staging
2. git add gittest2.txt
3. Use git status one more time to confirm that gittest2.txt is now in the staging area
4. git commit -m "add gittest2 file"
5. So far, we have made 2 commits

Generally speaking, most programmers use the command:
- git add .

Discussion: Can anyone explain the difference between 'git add <file name(s)>' and 'git add .' as often used by devs?

# Explaining the Git log Command

# Demo 7
1. Run the following command:
- git log

The git log command provides details including:
a. The commit ID
b. The Author who made the commit
c. Commits already done
4. Date and time of the commit

How did Git get to know these details?  It uses a configuration file.  The configuration file saves messages, IDs etc.

Use the command:
- git log --oneline
and notice that the first 7 characters in a commit ID can be used as a unique ID for that commit.  This can be called the unique sha.

# Explaining Git commits further
Git follows the concept of atomic commits.  The idea behind atomic commits is that you do one task at a time.  

Rule of Thumb: Keep commits centric to one feature, one component or one fix.  E.g. if you're fixing 10 bugs, please keep one commit to one bug.  There is also a debate about how you write commit messages.
The official recommendation is use the present tense, but imperative (i.e. give an order or command to your code base)

# GIT CONFIGURATION FILE
How does Git know my name, my email and which text editor to use.  We will also look at the .gitignore.  To handle the configuration file, we use the command:

- git config command

There are two ways of configuring the Git configuration file:
1. Global: This configuration is system-wide.  Anytime you make a Git repository, it interacts with the global file
2. Repository: You can keep your configurations local to a given repository.

Usually, people always keep configurations global especially the name and email; e.g:

- git config --global core.editor "code --wait"
- You can also use Ctrl+Shift+P on your Windows PC VScode window and type code to chose 'Shell Command: Install 'code' command in PATH' which makes your computer aware of the 'code' command in PATH and installs the code there.
- You can check how to use other code editors on Google.
Note that the command line expression for VScode is normally 'code'.  Also note that you can check the syntax for the config command in the documentation reference earlier mentioned (https://git-scm.com/docs):

git config - Get and set repository or global options.  To set up your name and email, for instance, you can use the command:

- git config --global user.name "Uche"
- git config --global user.email "uchedevops@gmail.com"

This is critical as Git would need to use your name whenever you make a push (or upload code)

# .gitignore
This is a special kind of file read only by Git itself and you have to create this file yourself.  It is used for:
1. Files you don't want to track
2. Node modules, API keys, secrets etc
3. You can get the .gitignore template online but note that you would need to master the patterns


# GIT FOR BEGINNERS: DAY 3: 20 APR 2025

# REFRESHER
Review of assignment.  

Using day 2 assignment, we proceed to commit:

# Demo 8
1. Run the following command:
- git status
- git add . (Create more files like .env, folder like folder2ignore, etc and add them on the .gitignore file - note that folers need to be written as: folder/)
- git commit
- And check to see what was committed

We then commit these changes with git commit without the -m option and see what happens (with git add . command as above and see what happens when we issue the git status command).  Notice the COMMIT_EDITMSG window on VS Code and note that 
this is because we have configured the default text editor to 'code' (ie. VS code). We will study COMMIT_EDITMSG further in coming sections. 

How do I know what to put in .gitignore then?  You can Google for .gitignore generator (e.g. Toptal .gitignore Generator).  You can then put the language you are writing code on to generate a .gitignore file you can literally copy and 
use in your code.

Assignment: Install the VS Code extensions for .gitignore generator and use those to generate your .gitignore files.

# Exploring the Git Configuration file further...
By the way, introduced the Git configuration file as where global configuration e.g user names, user emails etc are stored.  But where is this file located?

# Demo 9
1. cd to your home folder (Windows: c:\user\<User name>, Mac: /Users/apple etc)
2. Use the command more .gitconfig (in Windows) or cat .gitconfig (on Mac etc) to view the .gitconfig file.

This is the global configuration file.  It is broken down into blocks such as user, commit, core etc.  Note that you can edit this file (but of course, if you know what you're doing).

# So How Does the Commit Work?
Using the command: git log --online, we notice these - (HEAR -> master).  What does this mean?  Let's explain that.

In Git, every commit is dependent on the previous commit except the first commit. Notice that each commit is identified by a hash (unique sha), a commit message, which is some information about the commit etc.

However, the git log --online output does not show that the current commit is dependent on the previous commit (checkpoint) as it is a tracking mechanism.  The first hash has a parent that points to null, info that lists things like
author, email addy etc of the commit; the second commit points back to the first commit (i.e. the first commit's hash and parent, etc.  In same vein, the third commit points back to the second commit and so on and so forth.  

We can demonstrate these using a whiteboard session and a demo too.

# Demo 10
1. Go to your repo folder and issue the command ls -la to display a long listing including hidden files.
2. We identify the .git hidden directory and cd into it
3. list the contents (including hidden resources) of the .git folder using the ls -la command
4. One of the files in the .git folder is the COMMIT_EDITMSG. Rings a bell?  This is the file we opened up when we ommitted parsing the commit message with the -m option in the command: git commit.
5. Note that you can list your hidden folders on the VS Code GUI by using the Ctrl+commar keys (choose Files and scroll down to the Exclude session etc), remove **/git and you'll be able to see all your hidden folders.
6. Our focus here is the HEAD.  Notice that the HEAD file is pointing to master.  Remember we mentioned that in Git, you're always on some branch or the other.
7. Other folders in the .git directory includes hooks.  You can decide what happens before or after a commit by using sample templates in the hooks folder.  However, hooks are beyond the beginner course content. We also have the
   info and logs folders.  The logs folder is where we keep all the logs of what happened in our repository


# GIT BRANCHES
To explore branches and how applications are built, let's go into our second folder: gitspace2.  Note that we have been working on gitspace one thus far. This provides an opportunity to practice all we've learnt so far:

# Demo 11
1. cd to gitspace2
2. Run the git status command on gitspace2
3. When you get the 'fatal: not a git repository...' error message, initialize the repo.
4. git init
5. Use the git status command one more time to check the folder this time.
6. You should see messages like: On branch master, No commits yet, nothing to commit...

BTW, what is branch master? Also, on the left hand bottom of your VS Code, notice that it says 'master'.  Let's run some more commands before understanding what 'On branch master' means

7. Create a couple of files and folders using: touch index.html
8. Run the git status command.  What do you expect in the output of this command?
9. Use: git add index.html command to add this change to staging area
10. Confirm your change is now in the staging area using... what? git status command
11. Commit your changes using the command: git commit -m "add index file"
12. Check to see index.html on your VS Code Explorer.  Also note that you can use Ctrl+r to show hidden .git folder created by git init command.
13. Now run the command:

- git branch

You will notice the following output: * master.  This actually a pointer (the asterisk symbol stands for a pointer pointing to the master as the branch we are at).  What's the branch

# Understanding Git branches...
A branch is a new and separate version of the main repository. Let's explore a hypothetical scenario to explain what a branch is in Git.

Assuming you have an existing large application project with its codebase, and you need to add a new feature or fix a bug in that project, how would you do that in Git?  Your approach may be similar to the steps below.

a. Take a new copy of the entire code base; modify the codebase to add that new feature without tampering with the existing copy.
b. Assuming the ask is to fix a but, we take a copy of the codebase as well and modify the code to fix the malfunction
c. In Git terms, by doing the above, we have created a new branch from the main project called fix-error
d. Also, we have created a new branch to add the new feature called feature-more branch.  Note that the two new branches are unrelated.
e. After fixing the bug, we merge the fix-error branch to the main branch
f. Go back to the fix-error branch and complete the new feature code on this branch.
g. Merge the new feature branch with main branch.  

Hence, branches permit us to work on different demands of a project without impacting the main branch.  However, we only add our 'branch work' with the 'main branch' (by merging the new branch to the main) after we complete our tasks on 
the new branches.  However, notice that we have been using the terms main and master interchangeably.  A bit of history exists here where it was a bit impolite (or poilitically correct) to call the main branch 'main' instead of master
and slave terms, which sound a bit barbaric.

Hence, you will be asked to rename your master branch to say, main (main is the most popular name).

Therefore, HEAD -> master means...
Head points to where a branch is currently at.

To explain further, let's create a simple requirement - a html page:

# REQUIREMENTS 2
1.  Add the html code into the index.html file created above.  Your instructor will provide this.
2.  Run the git status and git add commands to stage the changes
3.  Commit with the command: git commit -m "Update index file code"
4.  Note also that HEAD still points to the master when we check with the command: git branch.  It also says same when you check the .git folder > refs > heads path on the VS Code Explorer.

# Demo 12
# How do we create more branches?
We can create multiple branches using any of the following methods:
1. Use the command git branch nav-bar
(Hint: This creates a branch for a dev in our team working on the Navigation bar.  Branch names can go after a company's naming standards)
2. Use the git branch command once again to check which branch we are at.  We notice our pointer still points to master!  However, we now have another branch.  Also confirm this on the Explorer window.
3. How do I move to a different branch.  We use the command:

-  git checkout nav-bar

4. Using git branch we notice the pointer is now pointing to nav-bar-feature
5. If we check the HEAD on Explorer, we notice it's now pointing to nav-bar-feature
6. Also notice what happens on GitLens
7. Create a new file called touch nav-bar.html
8. We can create the nav-bar.html code in a nav-bar.html file.
9. We go ahead and stage and commit the changes to the nav-bar.html file.



# GIT FOR BEGINNERS: DAY 4: 26 APR 2025
Last week we created a nav-bar branch and we were able to demonstrate switching to that branch.  Remember that we defined a branch as a new and separate version of the main repository.  Let's go ahead and create a nav-bar.html file thus...

# REQUIREMENTS 3
1.  Create a new file: nav-bar.html on VScode.
2.  Add the Requirements 3 code into the nav-bar.html file created above.  Your instructor will provide this.
3.  Run the git status and git add commands to stage the changes.  Ensure you are on the nav-bar branch.  Also check the GitLens output before and after step 5 below.
4.  Commit with the command: git commit -m "add nav-bar to codebase"
5.  Switch the branch back to master using the command: git checkout master.
6.  Immediately you switch to master, notice that the file you initially created (nav-bar.html) is completely gone on the GitLens UI.  Why?  The file was created by another dev and because we have not merged that code, master is oblivious of it.
7.  Notice that you could be working on completely different branch, file etc; however, it is critical to note that the HEAD always points to the current branch.  Hence, wherever your branch is latest, that's where the head will point.
8.  Also note at the same time, that you can get the head point to the previous commit(s) before the latest commit on a branch.  We will see that as we go.

In summary, here are the commands that we've learnt about and what they do with sample branch names:
a. git branch (shows all the branches available)
b. git branch wip-reports (creates a new branch called wip-reports)
c. git switch wip-bugfix (Same as git checkout - moves you to another branch
d. git log (shows a log of commits and their details)
Shortcuts also exist such as:
e. git switch -c wip-reports (creates a branch 'wip-reports' and moves you to that branch in one single command)
f. git checkout -b wip-bugfix (also creates a new branch and moves you to that branch in one single command)

NB: Always commit before switching to another branch

# MERGING BRANCHES
Git merge allows you to integrate changes from different branches to a single branch.  There are two types of merging:
- Fast forward merge
- Not fast forward merge

# Fast forward merge
Fast forward merge is always very easy to do.  Here you make less changes on the master by mainly making your changes on other branches, then merging that to master as follows:
- git switch master
- git merge wip-bugfix

In the above, you first make sure you are on the master branch (You merge from the branch you want to add another branch to.  In the above we want to add changes on wig-bugfix branch to master, so we first switch to the master)
And then we merge the changes in the wip-bugfix to the master.

# Not fast forward merge
In this case both the main (or master) and alternative branches are both being changed (or being worked on).  However, after some time you want to get all changes from both branches into one branch (say, the main branch).  To do this,
first of all make sure you are on the branch you don't want to move changes over to the other (in our case, the main branch as before).  Let's explore this.

# Demo 13
# How do we merge branches (Not fast forward merge)?
1. First ensure that the master and nav-bar branches have commits existing beyond the last merge
2. First of all, use the command: git status to ensure that the we are on the master.  If not, go to the master branch with the command: git checkout master
3. To merge the nav-bar branch to master use the command:
- git merge nav-bar
4. Take note of the output of the git merge command above on the terminal; for instance the message: nav-bar.html | 3 +++ means that all changes made were code additions (or insertions), not code deletes.
5. You can use the git log --oneline command to see those code insertions
6. Check out GitLens to see the changes on both branches, and then the merge to master nicely shown in graph form.
7. Note that some companies would demand you to delete the alternate branch(es) after merge.  This can be done with:
- git branch -d nav-bar
8. Run the git branch command to confirm we now only have the master branch
9. After running command 8 above, notice that GitLens retains a graphical view of your activities which shows that there was an alternative (and merged) branch called nav-bar.
10.  Why do most companies demand deleting the alternate branch which has been merged to main?  The branch has served its purpose, and if we need more branches we can create fresh ones!
11.  Let's look at the GitLens output and see what happens.

Class Workshop: Create another branch with another code file called footer.html and add code that the instructor would provide.  Add, commit and merge changes this branch to main. 

Group Assignment: Study Merge conflict, what causes them, and how to resolve it (resolve on VScode, terminal etc).  This should be presented next week Saturday

# GIT DIFF AND STASHING

# Git diff
The git diff command is an informative command that shows you the differences in same file!  These are differences in same file over time.  Hence, we refer to differences in versions of same file in x time and y time.  So you may be working with 
a file and you have staged that file, and you want to compare the difference between the file before it was staged and when it is staged.  For e.g., how does this file look say, 2 commits before and now, 2 commits after; or how does this same file look
or compare between this branch and another branch.

It is very important to understand this clearly.  Let's say we represent same file 1 as 'a' (at a moment in time) and file 2 as same file but represented as 'b' (at a later moment in time).  The following symbols seem confusing, but we will explain them as below.

- a = file 1 and b = file 2 (however, both are same file over time)
- --- file 1 (indicates changes in file, hence file a is represented by the minus symbol)
- +++ file 2 (indicates changes in file, hence file b is represented by the plus symbol)
- Note that the minus and plus signs above do not necessarily mean code removed or code added to the file.  They signify changes on the file over time.

Let's understand this further using a practical approach...


# Demo 14
1. On the terminal use the git status command to see the the state of things on your Git environment
2. Go to the index.html file and add the line: 'I would love to add nav bar here' after the <body> line
3. On the termina, run the git status command again to see that the index.html file shows modified
4. Use the git add index.html to add the changes to the staging area
5. Run the command:
- git diff
6. Notice there seems to be no output from the command
7. Run the command:
- git diff --staged
8. Notice the '--staged' option above provides us the desired output - the changes to the file, index.html.
7. Note that this output explains the 'a' and 'b' versions of the file as mentioned above including the '---' and '+++' symbols

Class Workshop: Edit the footer.html file also and run the git diff --staged command to see multiple outputs for differences in multiple files.

8. You can go ahead and commit the changes using the command below, for instance:
- git commit -m "update index and footer files"
9. Run the git log --oneline command to see what your logs look like.
10. Notice we can see the different commit IDs as the file kept changing over time.  We can use the commit IDs to show the differences in same file over time using the command below.

- git diff <previous commit ID> <later commit ID>

11. And we still get the differences in the file!
12. The git diff command with commit IDs can also be executed using a different syntax thus:

Assignment: Use branches with the git diff command to compare versions of same file across branches.


- git diff <previous commit ID>..<later commit ID>

# Git stash
To understand the Git stash, we use a workflow:

# REQUIREMENTS 4
- Create a repo, work and commit on main
- Switch to another branch and work (As you know, this may be required for bug fixes, new features etc)
- Note: Conflicting changes would not allow us to switch branch without commits

It's important to note that if you've worked on code or made changes that are NOT staged, Git may not allow you to switch to another branch without a staging or committing those changes. 

Let's understand this with a demo

# Demo 15
1. Run git status and ensure you are on the master
2. git swtich -c bugfix
3. git status to ensure we are on the bugfix branch
4. Modify the footer.html file by adding an extra line under the only line after the <footer> tag: 'trying to fix a bug'.
5. We are still in the middle of fixing the bug (we haven't fixed it) and we can jump off to the terminal and run the following commands
- git status (to ensure we are on the bugfix branch)
- git status (to check the status)
6. But your attention is needed on another branch (footer) by your colleague! Remember you have not completed
7. You switch to that branch with command: git switch footer (meanwhile your changes have not been staged)
8. You now have an error message - you can't move to footer (e.g. error: Your local changes to the following files would be overwritten by checkout...)
9. This explains the last note on Requirements 4
10. How do you solve this? You use the git stash command thus:

- git stash

11. You can now switch to footer with: git switch footer
12. You can see this when you run: git branch.
13. And you can switch back to bugfix using: git switch bugfix

We will explore more about the git stash command tomorrow.  


# GIT FOR BEGINNERS: DAY 5: 27 APR 2025

# git stash and git stash pop
Let's explore how git stash and git stash pop works

Going on with yesterday's analogy, after using git stash to save your changes, you were now able to switch to footer using: git switch footer

# Demo 16
Assuming we are through with helping our colleague from the example above, we are now ready to continue with our initial work on the bugfix branch thus:
1. Command: git switch bugfix (to switch back to the bugfix branch)
2. Command: git branch (to ensure our HEAD points to the bugfix branch)
3. When we check on VSCode we notice that the changes we made before exiting the bugfix branch do no longer exist on VScode.  Why?
4. We stashed those changes

NOTE: The stash is a temporary shelf where you can keep your code temporarily.  But you need to pick back your code from the shelf to continue. You do this using the command:

- git stash pop

5.  When you check the file now (after the git stash pop command), you now have the stashed changes back (checking from VS Code).
6.  Note also, that you can pop into another branch (from a stash done on a different branch) using same git stash pop command.
7.  Hence it's very very important to be careful with how you stash and pop... Hence the command:

- git stash list

8. The above command shows which branch where the work in progress was at before the stash e.g:
- stash@{0}: WIP on master: 9dd87fa change index and footer
9. And you can dump the stash you really intend to dump thus:

- git stash apply stash@{0}

NOTE: git stash should be used temporarily only.

Assignment:
Please explore these commands and submit during the week:
1. git checkout <commit id> - you could use the command: git log --oneline to see the commit hashes. Commit ID here is first 7 (hash)
2. git switch main (re-attach head)
3. git checkout HEAD~2 (2 commits prior)
4. git restore filename (get back to last commit version)
5. git reflog













