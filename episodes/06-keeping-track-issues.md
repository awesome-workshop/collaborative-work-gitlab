---
title: "Keeping things in order"
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

Whether it's a personal project of your own or a shared repository, keeping track of tasks in issues is a good practice.

Issues help inform all contributors about missing features, work in progress, or topics for discussion. They can also be used to report bugs. GitLab lets you select from three different types of issues — Incident, Issue, or Task — but these only differ if you have defined separate templates to guide contributors in providing useful information. 

Issues can be assigned to project members closed through merge requests. The [closing can be automated](https://docs.gitlab.com/user/project/issues/managing_issues/#closing-issues-automatically) by using `closes #<issue number>` in the commit message. Similarly, `related to #<issue number>` links a commit to an issue, which helps tracking progress.

Issues can be labeled based on their content, difficulty, urgency, status of work in progress, or other properties. The labels can be defined for each project separately, and a default set of labels can be easily generated from **Manage -> Labels**. Labels are helpful in search in large projects.

Issues can be viewed in an issue board, and be connected to a milestone. They can be set up **Plan -> Issue boards** and **Plan -> Milestones**.






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

In practice, for small projects, if you are the only contributor to your repository you would close your own issues. Nevetheless, issue tracking is still helpful.


::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 06.2

Explore setting up and using an Issue board. In addition to the default "Open" and "Closed" lists, add some others, for example "In progress" and "Help needed".


:::::::::::::::: solution

Follow **Plan -> Issue boards**.

To add lists, you will first have to define the corresponding labels in **Plan -> Issues**.



:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 06.3

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