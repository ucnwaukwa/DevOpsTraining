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

# REQUIREMENTS
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




  











   










