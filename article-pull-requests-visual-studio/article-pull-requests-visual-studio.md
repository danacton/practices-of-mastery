This article shows how to use pull requests as a code review mechanism in Visual Studio, Git and TFS. 

This content is complemented by the content on visualstudio.com on [Pull Requests](https://www.visualstudio.com/learn/git-pull-requests/) and [Pull Requests in TFS](https://www.visualstudio.com/en-us/docs/git/pull-requests).

# Use Git as you version control system
When you're creating your project in TFS, you'll need to set it up to use Git as the version control system. 

# Make your changes locally, on a branch
You will code as you normally do, making changes in your local copy of the Git repository for your project. The difference is that when you work locally, you need to do so on a branch. There are many branching strategies, the one we're working with here is the Git Flow branching strategy. You can read more about Git Flow [here](https://chriskirby.net/blog/streamline-your-tfs-to-git-migration-with-gitflow).

# Create a Pull Request from Visual Studio
When you are ready to push your changes to the remote repository (i.e. share it with the wider team and make it part of the codebase), you will create a Pull Request. This will create the point where someone can review your code.

To create a Pull Request, select the _View_ menu, then _Team Explorer_, then click _Pull Requests_, and finally click _New Pull Request_.

Be careful to enter enough detail about what the Pull Request is for. Also, be sure to assign the Pull Request to the correct people so that they can review your code.

# Respond to feedback
The reviewer of your code might have some questions/comments about your code, which might require you to make some changes. Go ahead and make those changes on your local copy of the project and push the changes to the TFS server from Visual Studio. You may have more than one push as you you might have more than one change to make based on feedback.

Once you have satisfied the reviewers, you can complete the Pull Request by clicking the _Complete_ button in the Pull Request view. You will also merge the code back into the branch upon which your branch is based in this flow. Once that is complete, you can delete your feature branch and sync your local copy of the repo.

