---
title: "Undoing things locally"
teaching: 10
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- Phew! Luckily I haven't pushed yet — how can I change my commit?
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand Git logs
- Exercise with local commits
::::::::::::::::::::::::::::::::::::::::::::::::

## Local commits?

Most Git tutorials start by explaining how to make local commits, track them, and use them during development on your local machine. Good habit if you do!

However, in practice, many of us only run `git commit` right before pushing our code to the remote repository.

Sometimes, you might want to change a commit — for example:

- You accidentally included files that weren’t meant to be committed.
- You forgot to save some changes before committing.
- Something just went wrong and you need to fix it.

If you haven't pushed your commit yet, you only need to deal with your local repository — fixing things is straightforward at this stage.

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 02.1

Create a new repository in the GitLab area. Note that in the CERN GitLab instance, the default branch name is `master` while in GitLab.com it is `main`.

Clone it locally and create some files.

Commit them.

:::::::::::::::: solution

From the GitLab GUI, select "New project/repository"

![](fig/gitlab-new-repo.png)

Make it public and add README.

Clone it to your local area:

```
git clone git@gitlab.com:<your user name>/<your repository>.git
cd <your repository>
```

Note that you can copy the repository address from the GitLab web GUI:

![](fig/gitlab-clone.png)

Create some files, for example:

```
$ echo "some junk" > test.out
$ echo "my real work" > work.txt
```

Show the status of your Git area.

```
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.out
        work.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Add them and check the status:

```
$ git add .
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.out
        new file:   work.txt

```

Commit your updates:

```
$ git commit -m " Add my work"
[main 4cb5898]  Add my work
 2 files changed, 2 insertions(+)
 create mode 100644 test.out
 create mode 100644 work.txt
```

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

## Inspect your commit

`git status` shows the local changes that have not been committed yet.

`git show` shows the contents of your commit.

`git log` shows the commit history.


::::::::::::::::::::::::::::::::::::: challenge

### Exercise 02.2

Explore the format options for the outputs of `git show` and `git log`. 
How to print logs as a short oneliner for each commit?
Can you print out just the names of the files that have been changed in your commit?

:::::::::::::::: solution

See:

- `git log --help` or the [git log documentation](https://git-scm.com/docs/git-log)
- `git show --help` or the [git show documentation](https://git-scm.com/docs/git-show).

```
$ git log --oneline
4cb5898 (HEAD -> main)  Add my work
339a972 (origin/main, origin/HEAD) Initial commit
```

```
$ git show --pretty="" --name-only
test.out
work.txt
```

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

## Undoing things

The best guide on undoing things before commit is the Git documentation: https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things

Now as we made the commit already, we can either undo it first with `git reset --soft HEAD^` or use the option `--amend`.

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 02.3 - git reset

Read the [example](https://git-scm.com/docs/git-reset#Documentation/git-reset.txt-Undoacommitandredo) on how to undo a commit.

Then find out in the [documentation](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things) or in the `git status` output how to unstage a file.

Commit with your updated changes.

:::::::::::::::: solution

```
$ git reset --soft HEAD^
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.out
        new file:   work.txt
```

You can check the logs to see that your recent commit is now gone:

```
$ git log --oneline
339a972 (HEAD -> main, origin/main, origin/HEAD) Initial commit
```

Then unstage as instructed, and commit again:

```
$ git restore --staged test.out
$ git commit -m " Add my work"
[main 3de58c2]  Add my work
 1 file changed, 1 insertion(+)
 create mode 100644 work.txt
```

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 02.4 - amend

In case you did the previous exercise, recreate another "junk" file and maybe do some changes to your other files.

Stage the updates with `git add .` and commit them. 

Now you realise that you did not want to commit the "junk" file.

Remove it from your local area and check `git status`. Do as instructed to update what will be committed.

Use `git commit --amend` to update your commit and verify the commit with `git show`.



:::::::::::::::: solution

You can do the following updates (or use your own):

```
$ echo "some other junk" > test.out
$ echo "Update my work" >> work.txt
```

Check the status:

```
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   work.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.out

no changes added to commit (use "git add" and/or "git commit -a")
```

Stage your updates and commit:

```
$ git add .
$ git commit -m "Update my work"
[main 77b681d] Update my work
 2 files changed, 2 insertions(+)
 create mode 100644 test.out
```

Whoops! That junk file ended up in your commit. 
Remove it and check the status

```
$ rm test.out
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    test.out

```

Update what will be committed as instructed:

```
$ git rm test.out
rm 'test.out'
```

and amend your commit:

```
$ git commit --amend
```

Whoa, what's this now?!

```
  GNU nano 4.8         [...]/gitlab-tutorial-test/.git/COMMIT_EDITMSG
Update my work

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Tue Aug 12 16:44:39 2025 +0200
#
# On branch main
# Your branch is ahead of 'origin/main' by 3 commits.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#       modified:   work.txt
#












                                                   [ Read 14 lines ]
^G Get Help    ^O Write Out   ^W Where Is    ^K Cut Text    ^J Justify     ^C Cur Pos     M-U Undo       M-A Mark Text
^X Exit        ^R Read File   ^\ Replace     ^U Paste Text  ^T To Spell    ^_ Go To Line  M-E Redo       M-6 Cop
```

Not familiar with NANO? Here's a cheatsheet if needed: https://www.nano-editor.org/dist/latest/cheatsheet.html

Or change it as instructed in the [git config documentation](https://git-scm.com/book/en/v2/Appendix-C:-Git-Commands-Setup-and-Config).

If you are happy with the commit message, just hit Ctrl-X to exit and you will get a confirmation message of your commit. If you want to change the message, just edit it, hit Ctrl-X and confirm with Y.

Check that your commit now has only your work file:

```
$ git show --pretty="" --name-only
work.txt
```



:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- Git command outputs are helpful, in particular, `git status`.
- Git is a powerful tool with a solid documentation.

::::::::::::::::::::::::::::::::::::::::::::::::