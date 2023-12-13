# Forking repositories

This is a follow up to the previous tutorial on GitHub. If you have no idea of what a "commit" is, please refer to the previous tutorial before coming to this one.

## What is the fork is a fork?
From the GitHub documentation: "A fork is a new repository that shares code and visibility settings with the original “upstream” repository.". In other words, a fork is a copy of a repository from another account into your GitHub account. Different from when you clone a repository, you are not making the copy into your local machine, you are making it in your GitHub.

## Branching vs Forking
Why would we use forks in the first place when we can you just branchs?
What can happen is when you are in a team with multiple people, a lot of branching can happen and that pollutes the main repository. So you might end up having more 10 different branches that you need to look at to find the one you are trying to actually merge in.

With forking, all the branchs you are working on stay within your copy of the repository and will only be visible to the main repository when you say so.

If you think about it, forking is a divide and conquer algorithm! You divide the branches into repositories for each person and then when everyone is ready, everyting gets merged in (conquered).

# IMAGE


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
Step 1. Go to the repository you want to fork. For this tutorial I will be using . If you were to

Step 2. Clone the fork into your local machine.

Step 3.


git remote show -n
git remote add name (upstream) location (main repo url)
git remote show
git fetch upstream
git branch --set-upstream-to upstream/main
git status
git checkout -b issue/num-description
git commit
git push -u origin branch-name
open pr from ur fork to main fork (to develop)
two people: (working on somebody else's fork)
git remote add name (elias) location (elias' fork)
git fetch elias
git checkout branch-name (might have to specify the fork, call for help)
git commit, git push

### GLOSSARY OF TERMS
- fork:
-

### LIST OF COMMANDS
- git remote show -n
- git remote add name (upstream) location (main repo url)
- git remote show
- git fetch upstream
- git branch --set-upstream-to upstream/main
- git status
- git checkout -b issue/num-description
- git commit
- git push -u origin branch-name
- git remote add name (elias) location (elias' fork)
- git fetch elias
- git checkout branch-name (might have to specify the fork, call for help)
- git commit, git push
