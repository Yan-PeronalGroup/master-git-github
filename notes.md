To begin, open up a terminal and move to where you want to place the project on your local machine using the cd (change directory) command.

Next, you need to initialize a git repository in the root of the folder, run the git init command.

Then use git status command to see which files git knows exit.
What this basically says is, "Hey, we noticed you created a new file called XX, but unless you use the 'git add' command we aren't going to do anything with it"

The message at the end of the commit should be something related to what the commit contains - maybe it's a new feature, maybe it's a bug fix, maybe it's just fixing a typo. Don't put a message like "asdfadsf" or "foobar". That makes the other people who see your commit sad. Very, very, sad. Commits live forever in a repository (technically you can delete them if you really, really need to but it’s messy), so if you leave a clear explanation of your changes it can be extremely helpful for future programmers (perhaps future you!) who are trying to figure out why some change was made years later.

When you want to add a new feature or fix a bug—no matter how big or how small. The diagram above visualizes a repository with two isolated lines of development, one for a little feature, and one for a longer-running feature. By developing them in branches, it’s not only possible to work on both of them in parallel, but it also keeps the main master branch free from questionable code.

branch for testing

Fix bugs
Develop features in parallel
...
any changes to be made...




Let's say you are on the primary branch and want to create a new branch to develop your web page. Here's what you'll do: Run git checkout -b <my branch name>. This command will automatically create a new branch and then 'check you out' on it, meaning git will move you to that branch, off of the primary branch.

After running the above command, you can use the git branch command to confirm that your branch was created:

The branch name with the asterisk next to it indicates which branch you're on at that given time.

For this reason, git branch is tightly integrated with the git checkout and git merge commands.


staging environment and commit

A commit is a record of what changes you have made since the last time you made a commit. Essentially, you make changes to your repo and then tell git to put those changes into a commit.










From now on, git will know existing files in folder.




1. Opening - Slide 0
Thank you for attending this workshop. I am gonna walk you through some basics of Git and GitHub for version control and project management within organizations. You are expected to learn by doing. But no need to have pressures if you have not installed required software beforehand or could not catch up during the workshop. I will share the slides with you afterwards. You should manage to get Git and GitHub up to running on your machine by following each step in the instruction. Please feel free to pause me if questions are emerging during the presentation. Also, if you feel like a short break in between, please let me know. There is a lot to be covered. I will try to explain everything within 1.5 hours. So let's get started.

2. Overview
This is an overview of what will be covered in this workshop.

You will be learning what Git and GitHub is, how to set up environment on your local machine, basic git commands for version control, host local projects on GitHub, manage your project and collaborate with others on GitHub, showcase GitHub projects using Colab, in the end of this slide, you will find extra resources for learning Git and GitHub.

3. Introduction
Git is a version control system that allows you to keep track *of changes on files*, which could be python scripts or other types of documents. There are some similar version control system, such as *XXX*.

GitHub is a cloud-based hosting service that integrates git version control system. This means that you can host any git repositories on GitHub and easily collaborate with others on those git repositories/projects. Aside from that, GitHub also allows you to *manage* projects and be social on the platform. GitHub is not the only git hosting service but probably the most used one.

In conclusion, if you don't need cloud services or collaborate with others on the same project, you can use Git without GitHub. However, since Git is the heart of GitHub, you cannot avoid it while using GitHub. In this regard, before getting into GitHub for project management and collaboration, I will introduce how to use Git locally.

4. Prerequisites  
In order to use Git and GitHub, you'll need to install Git on your local machine and create a GitHub account.

5. Get started with Git
Since we have the environment set up, let jump right into Git. In this section,  you will be learning how to start a git repository, commit changes, create branches, and play with branches.

After the installation of Git, you can call it on command line interfaces (CLIs) or graphical user interfaces (GUIs), for example using PyCharm or GitHub desktop. Today, we will be using the vanilla Git. What you need to do is to open up your command prompt on PC or bash on Mac. On my end, I will be running command line on Jupyter Notebook.

First of all, you need to configure git username and email address by running 'git config --global user.name' and 'git config --global user.email'.

The first line here is telling Jupyter that the following lines are command lines. Since you are using command line interface, you can ignore the magic line and enter the rest lines on your command line interface.

This input will serve as an identity of any git-related actions on your local machine. It's worth noting that the username and email address basically have nothing to do with your GitHub account.

Now, we can start to create a git repository on the local machine. *Repository here refers a container XXX*.

Say I want to git the master-git-github project. Firstly, using this command to move to the corresponding directory.

Next, we are going to initialize the git repository.

Now, let's run git status to see the current state of the repository.

This message here is basically telling you that we are on the branch namely master and there are no commits yet. I will be explaining what branch and commit stand for shortly. Then git has found some files on my folder. These files are not defined as untracked files by git, which means git knows the existence of these files but won't do anything unless you use 'git add' to add files in staging environment. After that git will start to be prepared for tracking these files.

Let's say I want to track myscript.py. If your are now on an empty folder, you can create an empty python file on that folder. And run this command line.

Now let's use 'git status' and see what happens to the git repository. Ok, this basically says that a new file was added to the staging environment.

Next, we are going to create our first commit. A commit is like a snapshot of the files you just added to the staging environment, which basically records all changes since last commit. It was recommended to commit often and with informative name summarizing the changes. Since we created a new file in the repository, let's commit it with a message, 'docs: add myscript.py'. This message is basically telling you that, you have commit a change in master branch with a message balabala, this number is a unique id of the commit. By calling this id, you can check the git repository at the corresponding stage.

As I've mentioned many times, another essential compound in git system is called branch. A branch represents an independent line of development. Every git repository has at a primary branch or a root branch. In this case, it is named as master. This branch is usually for carrying finalized files. In order not to mess up the master branch, it is highly recommended to create a new branch and commit changes on that branch before the changes are finalized. The branch can be used in different ways according to user requirements. For instance, if you want to develop same features using different strategies and make a comparison, you can then create a branch for each strategy and compare them. Later on, you can decide which strategy to be merged to the master branch.

Ok let's get back to the git branch command. By running 'git checkout -b test', you can create a branch and switch from the primary/master branch to the newly created branch and start another development line. If you run 'git branch', this will tell you which branch you are now working on. There is a star in front of test, so you are now on test branch. Before switching to another branches, all the following changes will be documented on test branch, which basically means, the files that were tracked on master branch will stay the same.

Now, let's make some changes to the myscript.py and commit on test branch. As you can see here, all the changes are not attached with test branch. The tree graph will look like this.

After finalizing changes on test branch, you can merge it into the master branch. To do so, first you need to checkout master branch, then call git merge command to merge test branch into current branch. There will be a merge commit automatically generated. You can also assign a message to this commit. So now the tree graph should look like this.

So these are the most used git command. Hope everything is clear to you. So now it's been XX mins. We have enough time. Do you have any questions with respect to Git commands?

Now, let's move to the introduction of GitHub. This section covers these 4 topics.

So now you already have a git repository on your local machine, what you are going to do is to push this local git repository to GitHub. To do so, you'll need to create a container on GitHub. If you click the




Therefore, by switching between commits, you can take steps back and view the previous version of your files. I believe that most people tend to have files with a surfix indicating the number of versions. This could be a headache once you have too many versions to be archived, which means you may have lots of files in the folder. This is where one of the advantages of git for version control comes in. With git, you are actually working on the same root file, while the changes are recorded using git commit. By calling the commit ID, you can easily move around different version of the file.

Before getting to use git, what I tended to do is that duplicate a file and name the new file with the version number and start to make changes on this file. The problem here is that, you will be having lots of independent files. By using git commit, you can easily keep track on the changes of files and keep the newest version of your file. You can also easily moving around different versions by running corresponding git commands.
