---
title: "Keep things in order"
teaching: 10
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- How to use issues to keep things in order?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Opening issues
- Closing issues with merge requests
- Defining best practices for contributions
::::::::::::::::::::::::::::::::::::::::::::::::

## Keeping things in order

Whether a personal project of your own, or a shared repository, keeping track of things to do in issues is a good practice.

They are helpful to inform all contributors of things missing, work in progress or discussion. They can also be used to report bugs.

Issues can be assigned to project members, and they can be closed by merge requests. The closing can be automated through merge requests by using `closes #<issue number>` in the commit message. Similary, ` ... #<issue number>` connects a commit to an issue, which helps tracking progress.

Issues can be labeled based on their content, difficulty, urgency, or status of work in progress. These labels are helpful in search in large projects. 


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

### Exercise 06.1

As the owner of the exercise repository, describe a desired new feature in an issue.
Assign it to a developer (that's your exercise buddy).
Let them make the changes suggested in the issue and push it in a branch.
Review the merge request and merge it if you are satisfied.


:::::::::::::::: solution

https://docs.gitlab.com/user/project/issues/

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: callout
### Issues are helpful also for single-contributor repositories

In practice, for small projects, if you are the only contributor to your repository you would close your own issues. Nevetheless, issue tracking is helpful even in that case.


::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 06.2

Make a quick list of the work you have planned for your code. For real, not for the exercise repository we have been working on.

Could you add them as issues to the code repository?

:::::::::::::::: solution

That's on you and we come back to this at the end of the day!

:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- Issue tracker in GitLab is a convenient tool for a centralised discussion for code development in a repository.
- Issues are helpful for tracking the progress and sharing the work.

::::::::::::::::::::::::::::::::::::::::::::::::