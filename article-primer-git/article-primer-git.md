# A very quick primer on Git

[Git](https://git-scm.com/) is a distributed version control system. Other products which fall into the same category, which you might know, are CVS, Subversion and Visual Source Safe. Git can be used in a number of ways, including from the command line and from your favourite IDE. 

This isn't an exhaustive description of Git, just a set of things you can do to get up and running quickly assuming your system is set up for Git. 

## A Git flow: this article
Here's a quick example using Github and the command line. It should get you up and running quickly and help you submit content to [practicesofmastery.com](http://practicesofmastery.com). It was the flow used to create this very page.

If you need more detail, please have a look at the [Git documentation](https://git-scm.com/doc).

### Part 1: Clone this repo
You'll need a [Github.com](https://github.com) account.

`git clone https://github.com/danacton/practices-of-mastery.git`

### Part 2: Create a branch for your change
I've called it *article-primer-git*. Name your branches with care so that you know what they're for.

`git checkout -b article-primer-git`

### Part 3: Add some things, change some things, etc.
I just created a single file. As you go, you'll want to add any changes you have made to the local copy of your repository. You'll do the *add -> commit* combo a number of times (whenever you've made changes you're ready to commit). Here, the file I'm adding is in a separate directory, I've added that step here for completeness.

`mkdir article-primer-git; cd article-primer-git`

At this point, you'll create file(s), or update existing file(s).

`git add article-primer-git.md`

`git commit -m 'Added the article markdown file'`

### Part 4: Push your changes to the Git server
Now you've probably got a few commits to your local git repo. You want to push those changes to the server often so that you're safe. When you push to the server, it will take all your commits and store them. They'll go into the branch you're working on (but remember to use the -u parameter as below to tell it to use the remote branch with the same name as your local branch).

`git push -u origin article-primer-git`

### Part 5: Create a pull request
A pull request is when you ask someone that mantains your repo (or a branch you want to merge into) to review your code and combine it with another branch (sometimes *master*).

You create a pull request in the UI of the Git server. This is because you're attempting to merge code in the server repo, not your local repo. The details for how you do a pull request can be found in your Git server's documentation (e.g. Github, Bitbucket, etc.).

### Part 6: Merge and cleanup
Once your pull request has been merged, you should re-fetch the repo. You might want to change branch back to the master branch first. And you also might want to delete the branch you worked on, though that is optional.

`git checkout master`

`git pull`

`git branch -d origin article-primer-git`

