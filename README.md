# Collaborative work in GitLab

## Building the lesson

This lesson was built from a modified version of The Carpentries Workbench template lesson in https://github.com/awesome-workshop/workbench-template-md. The repository was created checking the option of including all branches and making it public. 

The content can be edited in the `main` branch and the GitHub actions generate and deploy the site to https://awesome-workshop.github.io/collaborative-work-gitlab/.
No attempt for a local build was made, and in principle, there is no need to install R or Pandoc. Note, however, that the content should be in [Pandoc-flavored Markdown](https://pandoc.org/MANUAL.html). If one wishes to test locally, the instructions are provided in [The Carpentries Workbench][workbench] documentation.

The setup instructions are in `learners/setup.md` and the separate pages under `episodes`.

The `md-outputs` branch shows after setting up the repository. No need to merge them.

The schedule shows only in the "Instructor view": https://awesome-workshop.github.io/collaborative-work-gitlab/instructor/index.html
Use this link if you want to show it.

## Notes

### Documentation

See e.g.

- https://carpentries.github.io/lesson-development-training/
- https://carpentries.github.io/sandpaper-docs/index.html


### Indents and unexpected code blocks

Note that double-indent (two tabs) or anything more that three spaces produces a code block. That's not necessarily what one would expect.
Also, in some special cases, in nested lists, the second level items might appear as a code block.
 
### Figures

Figures should be located under `episodes/fig`, and included, for example, with

```
![](fig/portal_screenshot_landing_page.png)
```