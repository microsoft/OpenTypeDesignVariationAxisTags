# Suggested Process for Submitting Changes using Git

Several different people will be submitting changes for this repository.
Inevitably, there will be merge conflicts that will need to be resolved when
a pull request with your changes is created.

The potential for merge conflicts is all the more likely when merging forks.
When you create a pull request to merge your fork back into the upstream
repo, then the entire contents of the repo need to be merged, not just the
files you have edited. While you have been editing one set of files, changes
may have been made in the upstream repo to other files. When your merge is
evaluated by Git, it may not be able to determine whether the differences in
one of those other files are intended as changes you are making (effectively
undoing other peoples' changes). In that case, there will be a merge conflict
that must be resolved manually.

If there are a lot of merge conflicts when your pull request is created, it
may take a while for the owners of the upstream repo to work through the merge
conflicts. This is an extra tax on them, and can also delay incoroporation of
your changes. 

To make the process smoother when you create a pull request, the follow workflow
for your changes can help. Some steps will require use of Git from a command
line.

1. First, it is assumed that you will be doing your work in a fork of the repo.
This process requires that you work in a local clone of your fork, not in the
remote via the GitHub Web portal. For details on creating a fork and then a
local clone of the fork see
[For a Repo](https://help.github.com/articles/fork-a-repo/).

2. Set up your local clone for syncing with the upstream remote. This is
described here:
[Syncing a fork](https://help.github.com/articles/syncing-a-fork/).

3. Before starting your changes, sync your clone with the upstream remote, and
then merge your master branch with the upstream/master. This is described in
the help page mentioned in the previous step.

4. Create a new branch in your local clone, and switch to that branch to
prepare your changes. You can call the branch whatever you like.

5. When you have finished your changes, commit the changes in your working
branch.

6. Checkout your master branch, and sync it with the upstream/master.

7. Checkout your working branch, and rebase it against the master branch.

8. Checkout your master branch, and merge your working branch.

9. Push your changes to the remote. (This is the remote of your fork, not the
upstream.)

10. Now create the pull request, with your commits squashed.

The key in this process is to arrange the history of your commits so that they
appear to be based on the latest changes in the upstream. In that way, when you
create the pull request, there will be few if any differences across the entire
repo other than the changes you are making, hence few or no merge conflicts.

By syncing your master branch with the latest changes from the upstream just
before you're ready to create your pull request, your master will reflect the
most recent changes in the upstream. Then by rebasing your working branch
against the master branch, that will replay your changes in the working branch
as being made based on the latest changes in your master branch. Then when
you merge commits from the working branch into the master, they can be
fast-forwarded without any merge conflicts. And, if no other changes are made
in the upstream between the time that you sync'd and when you create the pull
request, then the changes coming into the upstream repo can be a single merge
commit added to the end of the history.