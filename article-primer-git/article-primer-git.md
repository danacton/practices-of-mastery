# A very quick primer on Git

This isn't an exhaustive description of Git, just a set of things you can do to get up and running quickly. There's a description below which might help explain some of the terms.

## A Git flow: this article
Here's a quick example using Github and the command line. It should get you up and running quickly and help you submit content to [practicesofmastery.com](http://practicesofmastery.com). It was the flow used to create this very page.

If you need more detail, it's provided below.

### Part 1: Clone this repo
You'll need a [Github.com](https://github.com) account.

`git clone https://github.com/danacton/practices-of-mastery.git`

### Part 2: Create a branch for your change
I've called it *article-primer-git*. Name your branches with care so that you know what they're for.

`git checkout -b article-primer-git`

### Add some things, change some things, etc.
I just created a single file. As you go, you'll want to add any changes you have made to the local copy of your repository. You'll do the *add -> commit* combo a number of times (whenever you've made changes you're ready to commit). Here, the file I'm adding is in a separate directory, I've added that step here for completeness.

`mkdir article-primer-git; cd article-primer-git`

At this point, you'll create file(s), or update existing file(s).

`git add article-primer-git.md`

`git commit -m 'Added the article markdown file'`

### Push your changes to the Git server
Now you've probably got a few commits to your local git repo. You want to push those changes to the server often so that you're safe. When you push to the server, it will take all your commits and store them. They'll go into the branch you're working on (but remember to use the -u parameter).

`git push -u origin article-primer-git`

### Create a pull request
A pull request is when you ask someone that mantains your repo (or a branch you want to merge into) to review your code and combine it with another branch (sometimes *master*).

You create a pull request in the UI of the Git server. This is because you're attempting to merge code in the server repo, not your local repo.

## An introduction to Git
[Git](https://git-scm.com/) is a distributed version control system. Other products which fall in the same category, which you might know, are CVS, Subversion, Visual Source Safe. Git can be used in a number of ways, including from the command line and from your favourite IDE. There are many commercial and non-commercial tools which make using Git easier, some listed here.

## Git terminology and ideas

- A **repo** (short for repository) is a set of files and metadata (including version history)
- A **remote** is a Git server that you're working on. You might work on multiple origins at once
- A **branch** is a copy of a set of files and metadata in a repo. A branch is used to allow for simultaneous work on files without interference.

## Git clients
- Command line (most Macs and Linux distros come with this by default)
- GitBash for Windows

## Git servers
- Atlassian Bitbucket Server
- Microsoft TFS
- GitLab
- Github

## Git actions

These are the things Git can do, along with an explanation. The way you use them is specific to you client (e.g. a "git clone" on the command line is a few clicks in your IDE).

- **clone** - when you clone a repository

