# GIT FOR BEGINNERS

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

A couple of commands preceed the commit command and we need to understand these using the diagram below.




   










