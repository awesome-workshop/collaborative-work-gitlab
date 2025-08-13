---
title: Setup
---

## GitLab account

For these exercises, you can use the [CERN GitLab instance](https://gitlab.cern.ch/) (available to CERN users, with the user name as your CERN login name), or an account on [GitLab.com](https://gitlab.com/).

## SSH key

You need to authenticate to push code to the repositories. The most convenient is an SSH key:

- Check if you have a key already and if not create a new one: https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key
- Add it to your account: https://gitlab.com/-/user_settings/ssh_keys



## Working environment

::::::::::::::::::::::::::::::::::::::: discussion

### Note

We expect participants to work in a local Unix environment on their laptop although working through a remote connection to a central system such as lxplus at CERN is possible for this lesson.

If you are unfamiliar with the Unix shell, you can work through the exercises in [The Unix Shell](https://swcarpentry.github.io/shell-novice/) tutorial by Software Carpentry. 

Windows users: the Unix tutorial gives `git bash` as an option. However, for all work during the hands-on session:

- do **not** use `git bash`
- do **not** use `Power shell` (apart from installing WSL2)
- activate WSL2 and **use the Ubuntu terminal** that comes with it!

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### Windows

Activate [WSL2](https://learn.microsoft.com/en-us/windows/wsl/install#install-wsl-command) and use the Ubuntu terminal.

::::::::::::::::::::::::

:::::::::::::::: spoiler

### MacOS

Use Terminal.app

::::::::::::::::::::::::


:::::::::::::::: spoiler

### Linux

Use Terminal

::::::::::::::::::::::::

## Prerequisites

- Know how to clone or create a repository
- Have Git configured in the local environment:
  - check with
    ```
    git config --list
    ```
  - if email and name are not configured, add them with
    ```
    git config --global user.name "[name]"
    git config --global user.email "[email address]"
    ``` 
    (Replace `[...]` with your input, and keep the quotes around your name if there are spaces.) 
- Understand the concept of local and remote 
- Know how to add updates from the local area to the remote repository with the usual Git workflow, e.g.:

  ```
  git status
  git add .
  git commit -m "Message describing your new content"
  git push origin main
  ```