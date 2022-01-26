# GitHub actions

GitHub actions is efficient workflow automation on github. Leverage them to run code linters and automated testing on your code. A good starting point can be found on the official documentation: [Understanding GitHub actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)

:warning: Depending on the permissions of the repository, it may be necessary to make changes to the GitHub workflow through the repository website on GitHub.

## Super Linter
The GitHub [Super Linter](https://github.com/github/super-linter) action helps to validate all code in the repository and gives useful feedback on style and functionality. This is a very useful tool for code reviews. It is active in this repository. The workflow file can be found [here](https://github.com/jdstamp/ccmb-gists/blob/main/.github/workflows/super-linter.yml).

## Useful links
* [Creating GitHub actions](https://docs.github.com/en/actions/creating-actions)
* [Deploying with GitHub actions](https://docs.github.com/en/actions/deployment/about-deployments/deploying-with-github-actions)
* [Continuous Deployment](https://docs.github.com/en/actions/deployment/about-deployments/about-continuous-deployment)
