# Practices of Mastery

Welcome to the repo for the [practicesofmastery.com](http://practicesofmastery.com) website.

Since [practicesofmastery.com](http://practicesofmastery.com) is dedicated to spreading the knowledge of continuous delivery of software, it makes sense that contributing to the site uses some of the practices we espouse.

# Hey, I want to contribute!

Sweet! We totally want you to contribute. We also want you to be attributed with the contribution. And we want to make sure that everyone gets to share in the magical knowledge that you have to impart. Also, we hope that some people learn a thing or two by contributing.

Here's the process of contributing to the site. You can follow the [Very Quick Primer on Git](http://www.stage.practicesofmastery.com/post/a-very-quick-primer-on-git/) for an example with more detail.

### Naming conventions

- The name of the branch, directory and markdown file for your article must be named after your article, all in lowercase, prefixed by "article-" and spaces replaced by -'s.
- For example if your article is called "Some Interesting Things", then you will have:
  - branch: *article-some-interesting-things*
  - directory: *article-some-interesting-things/*
  - file: *article-some-interesting-things.md*

### Process

1. Create a GitHub Account (if you don't already have one) and upload your SSH key
2. Fork this repo on Github: [https://github.com/danacton/practices-of-mastery](https://github.com/danacton/practices-of-mastery)
2. Clone your GitHub fork onto your machine:

 git clone git@github.com:*<account_name>*/practices-of-mastery.git

3. Create a local branch for your article named after your article (see naming conventions above):

git checkout -b *<article-some-interesting-things>*

3. On that branch, create a directory named after your article (see naming conventions above)

mkdir  *<article-some-interesting-things>*

4. Write an article on a practice of mastery - choose from any of those indicated on the site. Create the article as a Markdown document named after your article (see naming conventions above)
5. Commit the article to your local git repo

git add *<article-some-interesting-things>/<article-some-interesting-things.md>*

git commit -m "*\<Interesting Commit Message>*"

6. Push your changes to the your Github fork of the repo

git push origin *<article-some-interesting-things>*

7. Repeat steps 5 and 6 as required to complete your article, once complete continue to step 8
8. Create a pull request on Github for your branch in your GitHub fork to the master branch of the upstream repo, i.e.[https://github.com/danacton/practices-of-mastery](https://github.com/danacton/practices-of-mastery)
8. Once the pull request is reviewed, your reviewer will merge to master of the upstream repo and let you know your article has been published


### Sync Your Fork

If you are going to make a second contribution to the Practices of Mastery if will be useful to sync your fork of Practices of Mastery with the upstream repo. That can be done as follows:

1. Add the upstream repo as a remote to your local git repo

git remote add upstream https://github.com/danacton/practices-of-mastery.git

2. Fetch changes made to upstream (if any)

git fetch upstream

3. Merge upstream changes into your master branch

git checkout master

git merge upstream/master

4. Push changes to your GitHub fork

git push origin master

5. Now start with step 3 of "Process" above

