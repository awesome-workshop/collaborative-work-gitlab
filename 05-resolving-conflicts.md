---
title: "Resolving conflicts"
teaching: 10
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- How to solve conflicts in code?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Rebasing your working branch to a recent updates in the default branch
- Solving conflicting edits in files
- Defining best practices for contributions
::::::::::::::::::::::::::::::::::::::::::::::::

## Enter panic mode!

Everybody is frantically working on the code repository. The owner commits straight to the default branch, developers push from their own branches… and soon, conflicts explode.

To keep the conflict on the code — not between people — we’ll practice breaking things on purpose and then fixing them.


::::::::::::::::::::::::::::::::::::: challenge

### Exercise 05.1

Exercise with your pair to add content to you shared repository in two different branches. Learn how to update your working branch with contents of the updated remote.

Use `git rebase`.

:::::::::::::::: solution

See https://git-scm.com/docs/git-rebase

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: callout
### Remember to update your local main/master branch!!!

Always remember to update your local default branch.

```
git checkout main
git pull
```

Do this every time when you start a new development.

::::::::::::::::::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::: challenge

### Exercise 05.2

With your pair, make local edits to the same file in the shared repository.
Observe the error messages when trying to push and learn to solve conflicts with confidence!

Exercise conflict solving on the GitLab Web UI and with the Git command line tools.


:::::::::::::::: solution

See https://docs.gitlab.com/user/project/merge_requests/conflicts/

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::




::::::::::::::::::::::::::::::::::::: keypoints 

- Git is the tool to handle collaborative work.
- Git can detect updates that are safe to integrate to your code, and it will ask you to decide in case of conflict.
- Getting conflicts is not a bug but a feature of any code development work.

::::::::::::::::::::::::::::::::::::::::::::::::