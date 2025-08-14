---
title: "Automate testing"
teaching: 10
exercises: 20
---

:::::::::::::::::::::::::::::::::::::: questions

- How to automate testing of code updates?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand basic GitLab CI/CD pipeline concepts
- Run your first CI/CD pipeline
- Define a test
- Use artifacts
::::::::::::::::::::::::::::::::::::::::::::::::

## GitLab CI/CD pipelines

CI/CD stands for Continuous Integration / Continuous Deployment/Development.
It means that all updates are immediately integrated to the codebase and their functionality is tested.

CI/CD pipelines are automated workflows that can be set to run on every push.
They can also be scheduled at regular intervals.

In GitLab, these workflows are defined in a file called `.gitlab-ci.yml`.

`yml` (or sometimes `yaml`) stands for "yet another markup language"... It is quite commonly used in various workflow definitions and fairly easy to read and understand.
Keep in mind, however, that intending counts.

We will first have a look at the template that GitLab suggest in the "Pipeline editor".

::::::::::::::::::::::::::::::::::::: challenge

### Exercise 07.1

On the exercise repository, follow Build -> Pipeline editor and click on ...

Inspect it, save it and follow ... to see it running.

:::::::::::::::: solution

While inspecting, observe:

- stages with default names `build`, `test` and `deploy`, see...
- that this a typical software industry pipeline structure that builds a tool that is then deployed


:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

## Exit codes

Remember that in the earlier exercises, the repository owner pulled the new feature branch to test it locally. This is something that could be done in an automated manner.

However, for that we need a test that either succeeds or fails so that the pipeline can interpret it.

Unix exit codes can be used for that. For any command, there's an exit code - either 0 for success or > 0 for failure. `echo $?` gives the exit code of the last command on a terminal. 

Scripts normally fail at the first command giving a non-zero exit code.


::::::::::::::::::::::::::::::::::::: challenge

### Exercise 07.2

Read about exit codes in  .
Exercise with shell commands.
Exercise with a python test or a shell script.

:::::::::::::::: solution


:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

Now we go back to the exercise repository, so just a reminder:

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

### Exercise 07.3

Add a test to the pipeline template.
You could test the contents of the files in the repository, or some other functionality.
Keep it simple, we'll get to the real work soon.


:::::::::::::::: solution



:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::

## Artifacts

In physics analysis, the outcome of the workflow, e.g. a result file or a plot, is the best indicator that the code works as expected. 

Such outcomes can be defined as "artifacts" in GitLab CI/CD pipelines and they can be accessed through the GitLab Web UI.

For example, the job log file is always available, see the output of the previous pipelines.

You can define additional artifacts, and they are by default available to all stages of the pipeline. Note that artifacts cannot be modified so if you plan to use output of a step and modify it in the subsequent step, you will need to make a local copy of it in that job.


::::::::::::::::::::::::::::::::::::: challenge

### Exercise 07.4

Add an artifact to your CI/CD pipeline.
Download it from the GitLab Web UI.


:::::::::::::::: solution



:::::::::::::::::::::::::
:::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- GitLab CI/CD pipelines are useful to test the functionality of the code updates.
- They can perform decicated tests or procude a sample output which can indicate that the code works as expected.



::::::::::::::::::::::::::::::::::::::::::::::::