## Contributing

To contribute code, we suggest the following workflow:

1. Create a [Github issue](https://github.com/ConductorTechnologies/ciohoudini/issues) (if one does not already exist) describing your proposed change.
2. On the Github issue page, choose **create a new branch**. You'll see instructions to fetch and checkout the new branch locally. This ensures that your branch is associated with the issue.
3. Make changes, ensuring that your code adheres to the guidelines.
4. Be sure to pull in the latest changes from `master` and merge or rebase if necessary.
5. Push the branch and create a pull request on Github. Add reviewers including the repo owner. 
6. Once the pull request is approved, merge into `master` in the Github UI.

## Deployment

CircleCI workflows are triggered when you push tagged commits to Github. We use [semver](https://semver.org/) tags and we only trigger workflows on beta tags, rc tags, (release candidates) and full releases. Other parts of the `semver` spec such as `alpha`, or `build` are not recognized. 

#### Version format:
* **Beta releases:** Example `1.2.3-beta.1`. These are intended for testing internally and are available from test.pypi.
* **Pre-releases:** Example `1.2.3-rc.1`. These are intended for testing by customers and are not available through the Companion app by default.
* **Releases:** Example `1.2.3`. These are intended for production use and are available through the Companion app.

Releases and Pre-releases must be unique on **pypi**. Beta releases must be unique on **test.pypi**.

### Deployment workflow

There is a tool called [`skulk`](https://github.com/ConductorTechnologies/skulk). It is a command-line wizard that you can use to facilitate deployment. It is installed if you installed `requirements_dev.txt` as mentioned above. We strongly recommend using `skulk` to deploy.

To deploy a new version:
1. After you've had your pull request approved and merged into `master`, pull master locally.
2. Run the `skulk` wizard. This will guide you through all the steps to deploy, giving you the option of a full release, a pre-release, or a beta release. 
3. . See the [Skulk documentation](https://github.com/ConductorTechnologies/skulk).

To deploy a pre-release or beta release based on unapproved changes:
1. Make sure you are on a non-master branch.
2. Run the `skulk` wizard. This will guide you through all the steps to deploy the pre-release or beta release.

NOTE: You can't make a full release with `skulk` from a non-master branch.


## Code Guidelines (WIP)

1. **Write tests.** 
2. **Write docstrings** 
3. **Comments smell**
4. **Refactor**
5. **Use a linter**
6. **Use Snyk**
7. **Yada yada**

## Code Reviews

[Pull requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) require review from the before merging to master.
