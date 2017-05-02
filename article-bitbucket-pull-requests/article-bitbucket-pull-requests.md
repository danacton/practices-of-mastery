Pull requests are a simple and effective way to do code review and collaboration in a shared
environment with little friction in your team.

Pull requests give you:
 - Complete diff (difference) of the changes to each file.
 - Automatic updates so you can see changes as they are made.
 - Inline comments so you can pinpoint change suggestions.
 - Tasks to help you keep track of what changes need attention.
 - Notifications for comments, commits, or approvals.

## Building better pull requests
Here are a few suggestions to make pull requests more effective:
 - Try to make the pull request small enough to review but large enough to give you the context of the feature, bug fix, or update.
 - Use @mentions  and in-line comments to guide specific reviewers to specific items in the code.
 - Ask reviewers to create Tasks for things which must be addressed for approval. This helps designate between suggestions and discussions and things which must be fixed.
 - An accurate description and links to any issues gives reviewers more context and better access to what they need to understand the problem or feature you're addressing.

## Create a pull request
 1. Click **Create pull request**.
 2. Select the branch with the changes you want to merge.
 3. Check the destination repository and branch.
 4. Add a title that can be easily recognized in notifications and the pull request list.

 -- image create-pull-req

 - **Source**: This is the source commit, branch, or fork you are merging. You cannot modify the repository of the source but you can change the branch so check to be sure you're merging the correct branch.
 - **Destination**: This is the repository, branch, or fork you are merging your change into. You can modify the path for both the repository and the branch.
 - **Title** and **Description**: This will be the display title in the pull request list and in notifications.
 - **Reviewers**: Pretty much describes itself. You can also use @Mentions in comments to get someone to look at just one specific piece of code but not be responsible for reviewing the whole pull request.
 - **Close branch**: When you select this the source branch will be closed automatically once the pull request is merged. The closed branch will no longer appear in your list of branches in Bitbucket.
 - **Diff** and **Commits**:
    - Diffs: Shows a comparison of the changes in your pull request to the files in the destination branch.
    - Commits: displays a list of all the relevant commits. This list will be updated with any commits to the files on the source branch until the pull request is either merged or declined.

## Add reviewers to your pull request
Select reviewers for this pull request to make key contributors aware of the changes and create an effective review. Every reviewer can comment on the pull request and with a single click give their approval. If changes are made to the code, they can see those changes as soon as the  new commit is made. Additionally, the contributors you invite can decide to stop watching the pull request with a simple click.
Add reviewers to the pull request when you create it by entering their Bitbucket username or email address to the **Reviewers** section of the page. Add reviewers to the pull request after it is in progress by clicking **Edit** button (between **Merge** and **Decline**) at the top of the request.

## Compare before issuing a request
Before creating a pull request, you should compare your outgoing requests to the destination repository. This tells you how much the destination repository changed while you worked on your fork or branch. You do this by comparing incoming changes.It is good practice to make sure that there are no incoming changes before you make your pull request.
If there are changes what do you do? It depends on your project workflow. For example, if you are working on a team your project workflow might require you to merge and test incoming changes before sending your outgoing changes back to the destination. To compare your source to the destination, do the following:
 1. Navigate to the repository with the changes.
 2. Press the **Compare** button.  
    The system displays the **Compare** page.
 3. Adjust the Source and Destination values so they match the pull request you anticipate making.
 4. Press **Incoming** to see how the destination has changed since you've been working.  
    If there were no changes on the destination repository, the dialog reports:  
    **There are no changes.**  
    If there are changes, the system provides you with some helpful tips for merging them into your local repository.

## Request the destination repo owner pull your changes
To create a pull request, do the following:
1. Navigate to the repository with the changes.
2. Press the **Pull Request** button.  
   The system displays the request form.
3. Complete the form as appropriate for your request.
4. Press **Create pull request**.  
   The system opens your latest request on the **Pull Request** page of the original repository.  
   To see the list of all the pull requests against this repository, you can click **Pull Requests** in the navigation bar.
5. Adjust the **Source** branch if necessary.
6. Adjust the **Destination** repository or branch if necessary.
7. Enter a **Title** and **Description** for your pull request.
8. Press **Create pull request**.

## Accept a pull request
Only a user with write permissions on the destination repository can accept or reject a pull request.
Any user with read permission in a repository can review the open, accepted and rejected pull requests.
The following procedure illustrates the steps in accepting a pull request:
 1. Go to your repository.
 2. Click **Pull Requests** in the navigation bar.  
    A list of incoming pull requests under the **Open** context.
 3. Click a pull request on the list.  
    The pull request details appear and the view defaults to the **Diff** context. You can also view the **Commits** or the comment **Activity** on the request.  
    -- Image goes here pr-withdescript_approval-sidexpand (1)
 5. Examine the request using the various contexts..
 6. If you decide that you want to merge the fork into your own repository, click **Merge**.
 7. Confirm the action if prompted. Bitbucket merges the changes into your repository, all on the Bitbucket server.

## Merge a pull request
Merging your changes is the final stage of the pull request process. Complete the following steps to merge a pull request:
 1. Click the **Merge** button. You'll see something similar to the following screenshot.  
    -- Image goes here merge_strategies
 2. (Optional) Update the **Commit message** with more details.
 3. Select a **Merge strategy** from the two options:
   - **Merge commit** — Keeps all commits from your source branch and makes them part of the destination branch.  
   This option is the same as entering `git merge --no-ff` in the command line.
   - **Squash** — Combines your commits when you merge the source branch into the destination branch.  
   This option is the same as entering `git merge --squash` in the command line.  
   For more details on these two types of merge strategies, refer to the rest of this section.
 4. (Optional) If you're merging two branches in the same repository, you can select the *Close source branch* checkbox to remove the branch from the list of repository branches.
 5. Click the **Merge** button.

### Merge strategies
#### When to do a merge commit
Select **Merge commit** when you want to maintain an exact history of changes. Merge commits are also useful if, as part of your workflow, pull requests are large in scope and you review commits individually. Because this strategy keeps all commits during the merge, you'll still see all commits from the source branch on the **Commits** page.
#### When to do a squash merge
Select **Squash** to make your commits list less cluttered, which results in less time to search for commits that introduce a bug (with a git bisect) and provides an easy-to-follow commit history. Because this strategy combines all commits when you merge, you'll only see one commit on the destination branch on the **Commits** page.

## Decline a pull request
Declining a pull request is the same as saying you don't want to ever merge the changes in that pull request in their current state. Any reviewer can decline a pull request so your team might want to establish a policy about when to decline verses when to leave the pull request open in a stagnant state.
Declining a pull request cannot be undone. Once you decline a pull request you will have to open a new pull request request to continue a review.
Declining a pull request has no effect on the branches (source or destination) so the changes in the source branch are still in that source branch.  
To decline a pull request navigate to the pull request and click the **Decline** button in the top left of the page.  
To view a declined pull request:
 1. Navigate to the repository with the pull request.
 2. Click **Pull requests** in the left hand navigation.
 3. Click **Declined**.
 4. Select the declined pull request you want to view.
The comments and tasks in a pull request are preserved after it is declined.  You can add more comments to a declined pull request, however, new changes pushed to the branch will no longer update the pull request.

## Resolve a pull request with conflicts
When it detects conflicts in a pull request's incoming code, Bitbucket cannot automatically accept and merge. If this happens, Bitbucket notifies you and instructs you how to proceed when you click **Merge**:
 -- Image goes here
To resolve these kinds of conflicts you pull the changes to your local repository and resolve them there.

## Manually merge pull requests locally
Sometimes it is a good idea to use a workflow where you test a changeset on your local system before accepting a pull request. You can do this with any pull request. The typical workflow is this:
Receive a pull request in Bitbucket.
Update your local repository with the incoming changeset.
Investigate and/or test the change set.
If you the change set is good, you merge it into your local repository. You may have to resolve some conflicts. Then, you push the local repository back to Bitbucket. Back on Bitbucket, the pull request is marked as accepted in the **Pull requests** tab. If you don't like the change request, you discard the changes locally and reject the pull request on Bitbucket.

##### Git command line example
This is a simple Git example of the procedure for pulling changes made by another user from a fork of a Bitbucket repository, back into the original repository also on Bitbucket.
Check for incoming changes *(one change detected)*.
```
$ git fetch && git log ..origin/master
  Password:
  commit 2f41d64e75f2b4f0405cbfb1d2f882882809c209
  Author: ANDREW <alui@atlassian.com>
  Date: Thu Sep 8 11:50:08 2011 +1000
  adding images
```

Check for outgoing changes (*no changes detected*).
```
$ git fetch && git log origin/master..
  Password:
  remote: Counting objects: 6, done.
  remote: Compressing objects: 100% (3/3), done.
  remote: Total 4 (delta 1), reused 0 (delta 0)
  Unpacking objects: 100% (4/4), done.
  From https://staging.bitbucket.org/alui/alui-git
   2f41d64..7e28ddb master -> origin/master
  Pull the changes into the local repository.
```

```
$ git pull
  Password:
  Updating 2f41d64..7e28ddb
  Fast-forward
    Thumbs.db | Bin 0 -> 11776 bytes
    file.txt | 4 +++-
    2 files changed, 3 insertions(+), 1 deletions(-)
    create mode 100644 Thumbs.db
```

## Check the build status on a pull request
If your vendor or build system runs a build when you make a commit, you can see the status of the build(s) on each commit.  
After you create a pull request, its **Overview** tab includes the build status for all the commits on that pull request. Click the **Commits** tab to see the builds statuses separated by commits.
-- Image goes here build_status_pr
The **Builds** column contains one of these statuses:
 - appears if all builds for that commit passed
 - appears if no builds for that commit failed and at least one build is in progress
 - appears if at least one build for that commit failed

From the **Commit** column, click the link to the commit that you want to see. On the right side of the commit page, you see the build status icon again and a link to more details. Click the link to see details of each build for the commit. The table that opens when you click a build status includes only the most recent status for each build, not a history of builds for the commit.  
 -- Image goes here build_status_commit  
You can also check the build statuses for a repository without creating a pull request. To see the build status on a commit, press **Commits** on the left side of the repository.

<sub><sup>This article is taken almost directly from (Atlassian's Working with pull requests)[https://confluence.atlassian.com/bitbucket/work-with-pull-requests-223220593.html]. Some modifications were made to the layout.</sup></sub>
