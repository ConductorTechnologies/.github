# Contributing to Conductor Client Tools

This document contains general guidelines for developers wishing to contribute code to any Conductor client tools and libraries. Please familiarize yourself with this before you submit a pull request. You'll find specific contributor instructions for individual tools in the `CONTRIBUTING.md` file in the respective repository.
Contributions are always welcome!

## Workflow

To contribute code, we suggest the following workflow:

1. Create a [Github issue](https://github.com/ConductorTechnologies/ciohoudini/issues) (if one does not already exist) describing your proposed change.
2. On the GitHub issue page, choose **create a new branch**. You'll see instructions to fetch and checkout the new branch locally. This ensures that your branch is associated with the issue.
3. Make changes, ensuring that your code adheres to the guidelines.
4. Be sure to pull in the latest changes from `master` and merge or rebase if necessary.
5. Push the branch and create a pull request on GitHub. Add reviewers, including the repo owner. 
6. Once the pull request is approved, merge it into `master` in the GitHub UI.

## Deployment

CircleCI workflows are triggered when you push tagged commits to Github. We use [semver](https://semver.org/) tags, and we only trigger workflows on beta tags, rc tags (release candidates), and full releases. Other parts of the `semver` spec, such as `alpha` or `build`, are not recognized. 

#### Version format:
* **Beta releases:** Example `1.2.3-beta.1`. These are intended for testing internally and are available from test.pypi.
* **Pre-releases:** Example `1.2.3-rc.1`. These are intended for customer testing and are not available through the Companion app by default.
* **Releases:** Example `1.2.3`. These are intended for production use and are available through the Companion app.

Releases and Pre-releases must be unique on **pypi**. Beta releases must be unique on **test.pypi**.

### Skulk

There is a tool called [`skulk`](https://github.com/ConductorTechnologies/skulk). It is a command-line wizard that you can use to facilitate deployment. It is installed if you installed `requirements_dev.txt` as mentioned above. We strongly recommend using `skulk` to deploy.

To deploy a new version:
1. After your pull request is approved and merged into `master,` pull master locally.
2. Run the `skulk` wizard. This will guide you through all the steps to deploy, giving you the option of a full release, a pre-release, or a beta release. 
3. . See the [Skulk documentation](https://github.com/ConductorTechnologies/skulk).

To deploy a pre-release or beta release based on unapproved changes:
1. Make sure you are on a non-master branch.
2. Run the `skulk` wizard. This will guide you through all the steps to deploy the pre-release or beta release.

NOTE: You can't make a full release with `skulk` from a non-master branch.


## Code Guidelines (WIP)

* **Write tests.** 
* **Write docstrings** 
* **Comments smell**
* **Refactor**
* **Use a linter**
* **Make clean commits.**
  - Check to make sure no unwanted files make their way into the repo. Ideally, add files one by one, checking as you go. This is easy with a git GUI such as the one in Vscode. 
  - Try to make each commit encapsulate one logical change, and give it a descriptive commit message.
  - If making changes to poorly formatted code, put formatting in a separate commit to logic changes, preferably before.
  - Don't blindly do: `git add . && git commit -m "some updates"`.
* **Use Snyk**
* **Yada yada**

## Code Reviews

[Pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) require review before merging to master.
