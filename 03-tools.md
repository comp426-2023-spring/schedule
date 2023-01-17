# 03 Tools: bash + vim + git

## 2023-01-17

### Agenda

- Command line basics
- shell
- bash: work without a GUI 
- vim: edit on the command line
- git: 

### Useful resources


#### Command line basics

[UNIX Shell: Summary of basic commands](https://swcarpentry.github.io/shell-novice/reference.html) - Software Carpentry

[Basic UNIX commands](https://www.unixtutorial.org/basic-unix-commands) - Unix Tutorial

#### VIM

[Getting started with VIM: The basics](https://opensource.com/article/19/3/getting-started-vim) - opensource.com

[Classic SysAdmin: Vim 101: A Beginner’s Guide to Vim](https://linuxfoundation.org/blog/classic-sysadmin-vim-101-a-beginners-guide-to-vim/) - The Linux Foundation

#### Bash scripting

[Classic SysAdmin: Writing a Simple Bash Script](https://www.linuxfoundation.org/blog/classic-sysadmin-writing-a-simple-bash-script/) - The Linux Foundation

[How to write Bash scripts in Linux](https://www.tomshardware.com/how-to/write-bash-scripts-linux) - Les Pounder, _Tom's Hardware_

#### Fun things to think about and try

[Why don't bootcamps teach the command line](https://davidnix.io/posts/bootcamps-teach-command-line/) - David Nix

[Building a web server in Bash - Part I](https://dev.to/leandronsp/building-a-web-server-in-bash-part-i-sockets-2n8b) - Leandro Proença

#### GitHub resources

[GitHub Docs](https://docs.github.com/en)

#### git resources

[git scm reference](https://git-scm.com/doc)

[git scm docs](https://git-scm.com/docs/git)

[Pro Git (2nd ed.)](https://git-scm.com/book/en/v2) - Scott Chacon and Ben Straub

[8 Advanced Git Commands Universities Won’t Teach You](https://betterprogramming.pub/8-advanced-git-commands-university-wont-teach-you-fe63b483d34b) - Joel Belton

[.gitignore File – How to Ignore Files and Folders in Git](https://www.freecodecamp.org/news/gitignore-file-how-to-ignore-files-and-folders-in-git/amp/) - Dionysia Lemonaki, freeCodeCamp

##### If you want to protect your delicate sensibilities from swearing:

[Dangit, Git!?!](https://dangitgit.com/en)

[Simple commands from Git: Git commands from when I was learning git](https://medium.com/all-things-devops/simple-commands-for-git-3a0c5d36b46e) - Devin Moreland

##### &%$@ that:

[git - the simple guide - no deep shit](https://rogerdudler.github.io/git-guide/) - Roger Dudler

[Oh shit, Git!?!](https://ohshitgit.com/)

[Developers swearing](https://twitter.com/gitlost)

### Notes

<!--
- Introduction
  - What is Git and what uses Git
- Git basic commands
  - Create new text file, then git init
  - Git init .
  - Git commit change + explanation
  - Connect to github repository
    - `$ git remote add origin git@github.com:username/new_repo`
    - `$ git push -u origin master`
  - Show how to undo an add
    - `Git restore –staged <file>`
    - `Git reset HEAD`
- Branching
  - Show creating a new branch
  - Show branches
    - `Git branch`
  - Explain how branching works
  - Swap to other branch, make modifications
  - Push to new origin branch
    - `Git push -u origin <branch-name>`
  - Show in github, swap between branches
- Merging
  - Merge new branch into master
  - Git merge master <branch-name>
  - Push and show changes
  - Delete old branch
    - `Git branch -D <branch-name>`
  - Delete old branch on origin
    - Git push origin –delete <branch-name>
- Commit history
  - Find commit id, checkout
  - Explain what HEAD is
  - Explain detached HEAD
    - Experimental state with no branch attached
    - Modifications will affect nothing and not save, unless added to a branch
  - Make modification and save to <alt-history>
    - Git branch alt-history
  - Checkout branch, no longer detached and push
    - Git checkout alt-history
  - Show resetting all changes since last commit
    - Git reset –hard **will destroy everything and can’t be undone
  - Show diff between origin/local + parallelisms in commit logs
- Pull Requests
-->
