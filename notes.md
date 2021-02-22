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





Thank you for attending this workshop. I am gonna walk you through some basics of Git and GitHub for version control and project management within organizations. You are expected to learn by doing. But no need to have pressures if you have not installed required software beforehand or could not catch up during the workshop. I will share the slides with you afterwards. You should manage to get Git and GitHub up to running on your machine by following each step in the instruction. Please feel free to pause me if questions are emerging during the presentation. Also, if you feel like a short break in between, please let me know. There is a lot to be covered. I will try to explain everything within 1.5 hours. So let's get started.

This is an overview of what will be covered in this workshop.
