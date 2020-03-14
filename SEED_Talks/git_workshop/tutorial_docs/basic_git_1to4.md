# Basic Git tutorial for sections 1 to 4

The basic idea for this tutorial will be to practice the commands as well as getting comfortable with using the commands.
This will also serve to link the conecpts to the commands.  

## Some context to the folder/project set up

You can find the project folder in this dir:  
`SEED_Talks/SEED_Talks/git_workshop/tutorial/basic_git_1to4`

The folder contents should look something like this:   
```bash
basic_git_1to4
├── a.html
└── .git
    └── ...
```

For some context, the `.git` folder is where the git repo/project is stored.  
The `a.index` file is what we will simulate as the project here.

Our current git status and git log look like this:  

```bash
# git status

On branch master
nothing to commit, working tree clean
```

```bash
# git log --oneline --graph

* 52a853b Init commit for a.index
```

```html
<!-- How our a.index file looks like -->

<h1>Hello world</h1>
```

## Moving items from the left to the right 
### git add
(This is from `working directory` to the `index`)

Now to start, we have the 3 places, `working directory`, `index` and `repository` looking something like this.  

**Some image here**  

Now as you do in a project, we would now like to add a new line(change the `a.index`) to our webpage.  
Editing to add in a new line,
```html
<!-- a.index -->

<h1>Hello world</h1>

<h2>I am adding the second line right here</h2>
```

After making this change, say we would want to move this to the `index` to stage this change to a commit.  
We will now be moving the left, from the `working directory` to the `index`.  

To do this, we would use `git add a.index(file_name_here)`  

After this it will look this,  

**Something of image**  

```bash
# git status

On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   a.html
```

We can see now that we have selected the file(and subsequently the changes) we would want in our next commit.  

### git commit

Now say this is all the changes we would want to place in this commit and we want to mark it in the repo.  
Now we would conecptually move this into the `repository` and make a commit in the `repository`.  

To do this, we would, `git commit`

And now after adding our message, our repo would look like this:  

**Some image here**  

```bash
# git status

On branch master
nothing to commit, working tree clean
```

```bash
# git log --oneline --graph

* f96fbab Adding second line to a.index
* 52a853b Init commit for a.index
```

And now look at that, we have successfully made a change and moved it to the left to commit it in git.  
With this, our change is taken into account for the repo and we can go back to this snapshot in time.  

## Looking more at status and diff

Here I want you to mainly try out using ths `git status` and `git diff` commands to get a 'look' at your current project.  
With this, I mainly want you to form a mental image of the project based on waht you see here.  

Previously, we already saw how the git status mainly tells us how the 3 places looked like.  

Now we can use the `git diff` command to get a closer look at the difference.  

Say I edited the `a.index` file again and I want to see the difference between the `working dir` and the `index`. (i.e. what I changed to the file but not staged)  

```bash
# git diff

diff --git a/a.html b/a.html
index 3cd4fc6..22f1465 100644
--- a/a.html
+++ b/a.html
@@ -1,3 +1,5 @@
 <h1>Hello world</h1>
 
-<h2>I am adding the second line right here</h2>
\ No newline at end of file
+<h2>I am adding the second line right here</h2>
+
+I am temporarily here for now to see a difference
\ No newline at end of file
```

Without any flags or additional commands, we can see the git diff lists out all of the differences of files in the project.  
Can you guess what I did here then?  

```bash
#git diff

diff --git a/a.html b/a.html
index 3cd4fc6..22f1465 100644
--- a/a.html
+++ b/a.html
@@ -1,3 +1,5 @@
 <h1>Hello world</h1>
 
-<h2>I am adding the second line right here</h2>
\ No newline at end of file
+<h2>I am adding the second line right here</h2>
+
+I am temporarily here for now to see a difference
\ No newline at end of file
```

```bash
# git status

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   a.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	b.html

no changes added to commit (use "git add" and/or "git commit -a")
```

You can also check out `git status -h` and `git diff -h` for more info on how to use the commands.  

## Moving stuff to the right

### git reset HEAD --file
This is mainly moving the `repo` to the right, to the `index`

Now moving along, let say we did those changes to `a.html` and we staged those changes(moved it to the `index` as well).  
However the problem now is that we do not want these changes to be commited, in this case, we want the `repo` and `index` to look the same again.  
We should thus now use `git reset HEAD a.html` here to copy the contents of the repo back into the index, so that the staged changes are removed, but the changes are still in the `working directory`.  

Remember, we are trying to not stage the changes(not have these changes be in the next commit), but we still want those changes as we might still be working on them.  
This situation is mainly when you do not want to commit unfinished file/changes.  

Now your situation should look like this,  

**some image beofre**

**some image after**  

```bash
# git status

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   a.html

no changes added to commit (use "git add" and/or "git commit -a")
```

As you can see we are now back to before staging the file.

### git checkout HEAD --file
Moving the file from the `index` into the `working directory`   
**Note: Take precaution when doing this because it will override your `working dir`**  

Now say we don't like our current change to the file and we want to go back how it was previously.  
For this we would want to copy the content of the `repo` into both the `index` and `working directory`, thus wiping whatever we did to this file.  
The command thus would be `git checkout HEAD a.html`.  

Note: Since this wipes the `working directory` and `index` are wiped, take precaution in doing this.  

And there you go, you can now easily move files to the left or right for the places.  

## Final notes for this tutorial

A note of caution here though, when doing operations like these, `we always try to be more specific than implicit`.   

This is espcially true for the more destructive actions like `git checkout HEAD` and `git reset HEAD`.   
Although this is mainly up to preference, for me I still add by the directories and files with `git add .`, but I would always `reset` and `checkout` individually.  
The only times when I `reset` by directories is when I want to throw away all changes, for this you should be able to figure it out :D.