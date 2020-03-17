# Basic Git tutorial for sections 5 to 9

## Detaching the head and looking around

For this section, please try and `git checkout COMMIT_ID` for the previous commit to look at the repo at that point in time for the commit.  

```bash
# git log

* f96fbab Adding second line to a.index
* 52a853b Init commit for a.index
```

After this, I want you to look a the `git log`.  
Notice how the pointers, `HEAD` and `master` are.

After you are don with this, reattach your `HEAD` back to `master`.

## Making your first develop branches

Now create a `develop` branch based off the `master` branch.  
`git branch BRANCH_NAME` creates a new branch based on the branch you are currently on.  

Now add 2 commits to the develop branch.  
1. Adding a new line to `a.html`
2. Adding a new file of `b.html`

Then switch back to the `master` branch and add a commit here.  
1. Add a different new line to `a.html`  

Now with this, checkout the different branches and look at their differences.  
Also look at the logs and use `git diff BRANCH1 BRANCH2` and `git diff BRANCH2`
See how the diff is produced differently

Can you see how the differences came about?  
Also notice how the `git diff` are different.  

## Now we want to merge  

Now say you are done with the changes on the `develop` branch and want it to also be on the `master`, you would merge down the changes.  

To do this, there are 2 ways:
1. Implicit merge
   1. `git merge develop`
   2. This merges develop down to your current branch
2. Explicit merge
   1. `git merge master develop`
   2. This merges the develop branch down onto the master branch

**Add image here on the merge**

Now after the merge I want you to look at the logs as well as checking out the different branches.  
Also look at the diffs.  

## Forcing and resolving conflicts  

Now this usually happens when you have a commit on say the `master` branches that changes `a.html` and in a merge, you have a commit that says `a.html` should be changed differently, a merge conflict will happen.  
To simulate this,  
1. `master` branch
   1. Add a commit on the `master` branch changing the third line of `a.html`
2. `develop` branch
   1. Add a commit on the `develop` branch changing the third line of `a.html` to something different

Now try and merge down the changes from `develop`.

Resolve conflict, chuan hao please come in here

Look at log, checkout and diff

## Looking at fast-forward  

Now you are developing again, thus you,  
1. Add a line to the `b.html` on the `develop` branch

Try merging it down.  
It will fast-forward merge

Chuan hao explain this part pls

Then reset and do again.


