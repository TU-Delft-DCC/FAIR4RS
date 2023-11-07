# Week 10 - Code Quality II

:::{admonition} Today's learning objectives
**Topics for today:**
- Automation with GitHub Actions or GitLab runners
- Automate testing and documentation generation
- Linters and formatters
- Code analysis and test coverage with SonarCloud


**What to expect**
By the end of the seminar we would like you to have an automatic workflow running in your repository.
:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](./code-of-conduct.md)
- Discuss previous assignments [20 min]
- Introduce assignments [15 min]
- Work on assignments [50 min]

## 🙋 Discussion and questions

:::{note}
**Questions:**
- Did you identify code smells in your code base?
- Did you manage to write and run a test?
:::

## Reflection on CI/CD

:::{tip}
**💡 Tip:** Add the FAIR card to your Github board to as a reference on code quality.
:::

### FAIR card - Code Quality

```markdown
_Essential_
- [ ] Project [organisation](https://coderefinery.github.io/reproducible-research/organizing-projects/)

_Recommended_
- [ ] Follow [PEP8 guidelines](https://realpython.com/python-pep8/)
- [ ] Use linter (e.g. [pylint](https://pypi.org/project/pylint/), [flake8](https://pypi.org/project/flake8/))
- [ ] Use a formatter (e.g. [black](https://github.com/psf/black), [yapf](https://github.com/google/yapf))
- [ ] Follow [best coding practices](https://alan-turing-institute.github.io/rse-course/html/module07_construction_and_design/index.html)
- [ ] Make use of [Continuous Integration](https://the-turing-way.netlify.app/reproducible-research/ci/ci-options.html)
```

Continuous Integration (CI) refers to the build and unit testing stages of the software release process. Every revision that is committed triggers an automated build and test. With Continuous Delivery (CD), code changes are automatically built, tested, and prepared for a release to production.

[GitHub Actions](https://docs.github.com/en/actions) is a Continuous Integration and Continuous Delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

GitHub Actions looks for workflow in the folder **`.github/workflows/`**. Let's look at the skeleton of a **`.github/workflows/<name_of_workflow>.yaml`** file. The Code Refinery has shared two GitHub workflows to get started with:

### Example 1: Deploying documentation
[Code Refinery materials](https://coderefinery.github.io/documentation/gh_workflow/)

:::{admonition} Show workflow
:class: dropdown
```yaml
name: Docs
on: [push, pull_request, workflow_dispatch]
permissions:
    contents: write
jobs:
  docs:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v3
      - name: Install dependencies
        run: |
          pip install sphinx sphinx_rtd_theme
      - name: Sphinx build
        run: |
          sphinx-build doc _build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: ${{ github.event_name == 'push' && github.ref == 'refs/heads/main' }}
        with:
          publish_branch: gh-pages
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: _build/
          force_orphan: true
```
:::

:::{tip}
**Tip** If you would like to have a feel for how unit tests work together with pull requests you can have a look at this python repo and try the workflow: https://github.com/wmvanvliet/gizmo
:::

### Example 2: Automated testing
[Code Refinery materials](https://coderefinery.github.io/testing/continuous-integration/)
:::{admonition} Show workflow
:class: dropdown

```yaml
name: Python package

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
  
jobs:
  build:
    permissions:
      contents: read
      pull-requests: write

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Set up Python 3.10
      uses: actions/setup-python@v3
      with:
        python-version: "3.10"
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        python -m pip install flake8 pytest pytest-cov
        if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
    - name: Lint with flake8
      run: |
        # stop the build if there are Python syntax errors or undefined names
        flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
        # exit-zero treats all errors as warnings. The GitHub editor is 127 chars wide
        flake8 . --count --exit-zero --max-complexity=10 --max-line-length=127 --statistics
    - name: Test with pytest and calculate coverage
      run: |
        pytest --cov-report "xml:coverage.xml"  --cov=.
    - name: Create Coverage 
      if: ${{ github.event_name == 'pull_request' }}
      uses: orgoro/coverage@v3
      with:
          coverageFile: coverage.xml
          token: ${{ secrets.GITHUB_TOKEN }}
```
:::



## Assignments for Friday 26th of May
The goal of the this week's challenges and assignments is to set up and run an automated workflow. 

### Assignment 1
Add a GitHub Actions workflow to your repository. We recommend to start with the provided Code Refinery materials and examples.

Some workflow options to consider:
- On which [Event type](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows) should the workflow run (push, pull request, [scheduled](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#schedule))?
- On which Operating System(s) should the workflow run?
- On which branches should the workflow run?



:::{tip}
**💡 Tips:** 
- GitHub has templates available. Go to the **Actions tab** in your repository and select **new workflow** for an overview.
- You can find [**workflow examples**](https://github.com/sdras/awesome-actions) shared in the community.
- Add **`workflow_dispatch`** as a trigger for your GitHub Actions workflow. With this trigger, you can [**manually run an action**](https://docs.github.com/en/actions/managing-workflow-runs/manually-running-a-workflow), instead of having to rely on external triggers. This is quite useful when testing your workflow.
- Test your workflow in a separate branch to avoid committing many small changes during debugging.
:::

:::{warning}
**🔧 GitLab pipelines**
The TU Delft Gitlab does not have preconfigured servers available to run [**Gitlab pipelines**](https://docs.gitlab.com/ee/ci/pipelines/), the equivalant of GitHub Actions. In order to set up a pipeline, you will need to request a TU Delft Virtual Private Server and configure a Gitlab runner there. The DCC has developed a [**step-by-step guide**](https://tu-delft-dcc.github.io/infrastructure/gitlab/gitlab_docker.html).
:::


### Assignment 2

We can use tools to perform quality checks on our software.

**Local quality check**  
The Code Refinery example on automated testing also contains a step called _Lint with flake8_. “Linting” means running a basic quality tool against your code. The tool will check your code syntax and provide instructions on how to clean it. You can run these tools both locally and in the cloud. Formatters not only check the code syntax, but also format it for you. For Python, a formatter would change your code to match the [PEP 8 styleguide](https://peps.python.org/pep-0008/). In short, linters flag bugs and bad practices and formatters fix your code to match style guides.

:::{tip}
**💡 Tips:** 
- List of [**linters**](https://github.com/caramelomartins/awesome-linters).
- List of [**formatters**](https://github.com/rishirdua/awesome-code-formatters).
- Formatters can be easily integrated with many editors such as Vim, Emacs, VSCode, Atom or a version control system like GIT. For example, we use a [**setup VSCode to run black on each save**](https://dev.to/adamlombard/how-to-use-the-black-python-code-formatter-in-vscode-3lo0) .
- Ensure all developers in your project use the same linter and formatter for consistent code quality.
:::

**Cloud-based quality check**  
To automate checking your code quality, we can also make use of a third-party service. [SonarCloud](https://docs.sonarcloud.io/) is a cloud-based code analysis service designed to detect coding issues in 26 different programming languages. The [free plan](https://docs.sonarcloud.io/organizations/payment-and-visibility/) allows you to analyse an unlimited numbers of **public repositories**. Private projects will not be importable on this plan.

1. Make your repository public.
2. Link your GitHub repository to SonarCloud via their [login page](https://sonarcloud.io/login).
3. Follow the [instructions](https://docs.sonarcloud.io/getting-started/github/) to set up the code analysis.


### Assignment 3
A common tool used in open software repositories, is the use of repository "badges", for example a license badge [![CC BY 4.0][cc-by-shield]][cc-by]. These badges can signal to fellow developers that you commit yourselve to shared standards software development. 

1. Have a look at the [**matchms software**](https://github.com/matchms/matchms) from the eScience Center on the badges they use to indicate the standards they follow. 
2. Add badges to your repository README. You can find badge templates at **https://shields.io**. Consider adding a Build badge for you new workflow or a Code quality badge for your SonarCloud analysis.

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg

## Materials

- [Code Refinery - Deploying documentation](https://coderefinery.github.io/documentation/gh_workflow/)
- [Code Refinery - Automated testing](https://coderefinery.github.io/testing/continuous-integration/)
- [SonarCloud - Getting started](https://docs.sonarcloud.io/getting-started/overview/)
- [Repository Badges](https://shields.io/)