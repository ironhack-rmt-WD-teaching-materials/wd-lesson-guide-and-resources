

# Git intro

<!--- 

Status: draft

@todo: record video

--->


Before git topics:
- how to open a terminal in VS Code
- common operations in the cli
  - see where I am: `pwd`
  - list files and directories: `ls` or `ls -al`
  - move to child directory: `cd nameOfDirectory`
  - move to parent directory: `cd ..`
  - autocomplete name of a directory: "tab" key
  - create a directory: `mkdir`



Topics:
- what is git & why it is useful.
  - keep track of changes
  - share code with other developers & integrate changes
- create a directory & go inside it: `mkdir git-demo` + `cd git-demo`
- initialize a repo: `git init`
- create a file: `touch index.html`
- create a file: `touch about.html`
- check current status: `git status`
- add to staging area: `git add index.html`
- check status again: `git status` (now file is added to staging area)
- (optional) un-stage: `git rm --cached <file-name-1>`
- make a commit: `git commit -m "msg"`
- see history: `git log`
- Git vs. Github
- Github: upload an existing repository
  - create a repo on github
  - push the repo we've created
- Github: fork & clone



## General guidelines for labs/assignments

General guidelines for labs/assignments:
https://gist.github.com/ironhack-edu/dd3635de73a6ef07ef337bf184eda985


## Cheatsheets


- GitTower:
  - [Git cheatsheet](../media/pdf/git-cheat-sheet-gittower.pdf)

- Git Cheatsheet from Github:
  - https://education.github.com/git-cheat-sheet-education.pdf

- Common Git Commands (most common commands with a very clear explanation):
  - http://guides.beanstalkapp.com/version-control/common-git-commands.html

  
## Resources to practice
- create a repo & play around
- Visualizing Git: https://git-school.github.io/visualizing-git/
- Git branches: https://learngitbranching.js.org/



