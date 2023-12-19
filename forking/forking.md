# Forking repositories

This is a follow up to the previous tutorial on GitHub. If you have no idea of what a "commit" is, please refer to the previous tutorial before coming to this one.

## What the fork is a fork?
From the GitHub documentation: "A fork is a new repository that shares code and visibility settings with the original “upstream” repository.". In other words, a fork is a copy of a repository from another account into your GitHub account. Different from when you clone a repository, you are not making the copy into your local machine, you are making it in your GitHub.

## Branching vs Forking
Why would we use forks in the first place when we can you just branchs?
What can happen is when you are in a team with multiple people, a lot of branching can happen and that pollutes the main repository. So you might end up having more 10 different branches that you need to look at to find the one you are trying to actually merge in.

<img src="branching.png" />

With forking, all the branchs you are working on stay within your copy of the repository and will only be visible to the main repository when you say so.

If you think about it, forking is a divide and conquer algorithm! You divide the branches into repositories for each person and then when everyone is ready, everyting gets merged in (conquered).

Instead of having a remote and local where you do branches from the local to the remote now you have 2 remotes and a local where you do branches from one remote to the other one. So things can get tricky here, so do not feel discourage if you struggle.


## Prerequisites
- Have experience with an operating system of your choice (macOs, Windows or Linux)
- Have experience using terminal commands
- Have a computer and stable internet connection
- Have a terminal installed of your preference, I recommend iTerm for macOS
- Have a text editor or Integrated Development Environment (IDE) installed (like VSCode)
- Have experience with branching on GitHub


## Table of Contents
- [Steps on Forking](#steps)
- [Glossary of Terms](#glossary)
- [List of Commands](#commands)


## STEP BY STEP GUIDE
Step 1. Go to the repository you want to fork. For this tutorial I will be using Obojobo's repository.

Note: the visibility of your fork will corelate with the visibility of the fork.

You have the option to change the name of the fork and the description. You can also decide if you want to copy just the main or all branches.

Once you are done updating all settings, you can click "Create Fork"

# IMAGE

After the fork is done syncing, you should be at a new page that says "github.com/USERNAME/repo-name", in my case "github.com/nizolnier/Obojobo"


Step 2. Clone the fork into your local machine. This can either be done with HTTPS or SSH depending on what you are using but do take a note of which one you are!

# IMAGE

Step 3. After cloning, it is time to establish a connection with UCFOpen's Obojobo. Right now, your local copy knows nothing, it doesn't know who is the parent repository.

You can verify this by doing ```git remote show -n``` and you will only see ```origin```.

# IMAGE

With new powers comes new vocabulary! From this moment on, we will be referring to UCFOpen's Obojobo as ```upstream``` or ```parent```, and our fork as ```origin``` or our fork.

With that in mind, let's add the parent connection!

Remember when I said that you needed to remember if you used HTTPS or SSH to clone? This is going to come handy right now.

Go back to your browser and open a tab to the parent repository (UCFOpen's Obojobo). Click on code and then copy the link to clone. If you used HTTPS before, use it now, same goes for SSH.

# IMAGE

Go back to the terminal and type the command ```git remove add upstream <ucf open's obojobo url>```.

# IMAGE

To check if the command work, run ```git remote show -n```, you should see ```origin``` and ```upstream```

# IMAGE

Step 4. Get the branches from the upstream, run ```git fetch upstream```

We need to get a copy of the main branch from the parent repository into our local machine so we can send pull requests to it.

# IMAGE

Step 5. Now before we create a new branch, we will set it's parent to reflect on the upstream with the command ```git branch --set-upstream-to upstream/main```

# IMAGE

Step 6. Create the branch and enter it with the command ```git checkout -b branchname```. For CDL, you will likely be working on an issue so follow the pattern of ```issue/description-of-issue```

# IMAGE

Step 7. Add files with ```git add .```

# IMAGE

Step 8. Now to push we will do ```git push -u origin branch-name```. The ```-u``` option automatically sets the upstream. That way, in the future, Git "knows" where you want to push to and where you want to pull from, so you can use git pull or git push without arguments.

# IMAGE

Step 9. Open a pull-request in the main repository.


## Special Version for Two People

If you are ever in a situation where there are two people working on the same part of the project

Step 0. Choose which fork will be the main fork. Do rock paper scissors or something to decide one fork only.

If you are the person who will have the main work, go ahead and create the branch for your peer. If not, then keep following this tutorial.

Step 1. In your terminal, do ```git remote add person-name <fork url>``` to make a connection with their fork. For example, if I am working with Bob (username is bobiscool) on a project, I would do ```git remote add bob github.com/bobiscool/Obojobo```.

# IMAGE

To check if the command work, run ```git remote show -n```, you should see ```origin```, ```upstream``` and that person's name (in my case, ```bob```)

# IMAGE

Step 2. Get the branches from the fork, run ```git fetch person-name```

We need to get the branch we will be working on.

# IMAGE

Step 3. Now, check out the branch with ```git checkout branch-name```. Here you might have to specify the fork, so this is the perfect time to reach out for help!

Step 4. Work on the files and follow the same commands as you are used to


### GLOSSARY OF TERMS
- fork: copy of a repository into your github account
- upstream: parent of the fork

### LIST OF COMMANDS
- ```git remote show -n```
- ```git remote add name (upstream) location (main repo url)```
- ```git remote show```
- ```git fetch upstream```
- ```git branch --set-upstream-to upstream/main```
- ```git status```
- ```git checkout -b issue/num-description```
- ```git commit```
- ```git push -u origin branch-name```

