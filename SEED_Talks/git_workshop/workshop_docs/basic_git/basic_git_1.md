# 1. The 3 important conceptual places(4)

Before starting to use git, I think it is a good idea to give you a good mental image and the concepts of how git works under the hood.  
This is important as to understand and remember what command/commands(there might be multiple ways and commands to do certain things) are doing, you will usually be trying to link the commands to the mental model of git.  

With that, we start off with the basics.  

## Main idea behind git
Although git itself is quite complicated and can be used for many different things, the main idea of what it is doing is always the same.  

`git tracks the changes made and creates a timeline of these changes`

Look at the diagram below(you can ignore some of the jargon in the picture for now), can you see how it looks like a timeline of events, only this time, it's changes.  

![placeholder for now]()

Some context:  
The `commits` you see here can be taught of changes you made in your code, like how you may have added or removed a line of text from a `index.html` file.
The arrows seen are also to show how commits are connected and thus show a progression of time.

We can see how the `commits` are linked together, with the `commits` on the left linking to the ones on the right. 
This also represents a flow of time, as the `commits` on the right are more recent than the ones on the left.  
As such we can see how small changes all build up to the current project.

However to create these `commits` and to see how they interact with the project in your working directory, we would have to look a bit deeper(More will be explained later on).

Below we will be focusing on how we can create these `commits` to have a single line of `commits` tracking the changes you made to your project linearly.

## Starting a project with git
Whenever you create a project, likewise you will also create a git repository in the project in order to have git working for your specific project.  
This might look something like this:  

```bash
some_really_cool_project (The project folder you created)
├── .git (the git repository)
│   └── ...  
└── some other files in the project
```

However, what you may not know is that git also then creates 2 other `'workspaces'/'virtual folders'` in this project that you may not see.  
One is called the `index` and the other is the `repository`.  

All together, now you have 3 `'workspaces'/'virtual folders'`, the `working directory`, `index` and the `repository`.

The way your project files(i.e. the `working dir`) mainly interacts with `git` is through these 3 workspaces.  
Thus for now, just take these things as it is and you will see the applications in the tutorials later.  

## Moving things to the left  

Now as you work on your project, you will makes some changes to a file(this can be `create`, `update`, `delete`, thus any of these counts as a change) you might say I want to now create a commit of my project here.  
This means you would like to take the changes you have made and bundle them in a commit so as to make a snapshot of your project at this point in time.  

Note: The commits themselves store the changes, but looking the project at the point in time of the commit is a snapshot of the project at this time.  

Now, your example project may look like this:  

**I think from here I can refer to tutorial**


## Moving things to the right

Like the above section, `moving things to the left`, moving things to the right follows the same conept.  
Instead of copying things from the right to the left, we do this from the right to the left.  

As such, this is dangerous because you can and will override your `working dir` without any further confirmation from the command.  

Now, imagine the scenario,  

**Refer to tutorial**


