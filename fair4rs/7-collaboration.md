# Week 7 - Collaborating on research software

:::{admonition} Today's learning objectives
**Topics for today:**
- Setting up a workflow for collaboration
- Write contributing guidelines
- Invite collaborators to your project

**What to expect**
By the end of the seminar we would like you to have defined and documented a workflow for contributing to your project.
:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](./code-of-conduct.md)
- Discuss previous assignments [20 min]
- Introduce assignments [15 min]
- Work on assignments [50 min]

## 🙋 Discussion and questions
👉 Go to [**collaborative document**](https://hackmd.io/@fair4rs/H1Yg6xVG2).


## Reflection on collaborative software development
:::{note}
**What we are not covering about collaboration in Today's assignments** 
- We are not covering collaboration that takes place in science such as preprints, drafts, reviews.
- How you collaborate with scientists in an open science way in general. 
- Instead we focus more on the software component in this seminar, this is how to take advantage of software development practices in the context of science.
:::

:::{tip}
**Things to keep in mind before starting the seminar**
-  All aspects we touch upon in the seminars are highly interconnected and interdependent.Just like everything in code development including the code, has to do with documentation, you can imagine everything can also be related to collaboration from code readability to actual verson control. 
- Today we want to figure out which collaboration aspects are relevant for your current phase. Furthermore we want to expose you to other practices that might be useful in the future.
- User centered criteria tells in a way what to do. Think of the practices we share today as things developers (as a type of user) have adopted because it makes their developer experience better.
:::

:::{warning}
**Reflecting on collaboration**  
- Do you expect contributions (in the future) from (external) collaborators?
    - Do different user types require different guidelines?
    - When would you make use of forks?
- What are the essential things you need to have in place so that peer scientists can collaborate with you in a research software project?
- How are you currently using branches to organize your work?
- Does your project require a stable version(s) to always be accessible? 
- Can you think of scenarios where rules and automation can improve social coding/collaboration?

:::


## Assignments for Friday 12th of May

The goal of the assignments is to define a workflow that allows users and developers (including yourself) to contribute to your (open source) project. The convention for open source projects is to write a contributing guide. This guide is the first place that new contributors will look to understand if your project welcomes contributions and what to expect. The goal of a `CONTRIBUTING.md` file is to increase the number of successful contributors to your project.

:::{tip}
**💡 Tip:** Add the FAIR card to your Github board to as a reference on FAIR collaboration on research software.
:::

### FAIR card - Collaboration
```markdown
_Essential_
- [ ] Make use of [Github issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)
- [ ] Provide contribution [guidelines](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors)

_Recommended_
- [ ] Choose a branching model ([DCC Guides on branches](https://tu-delft-dcc.github.io/software/git/branch_management.html))
- [ ] Make use of [issue templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)
- [ ] Provide a [Code of Conduct](https://www.contributor-covenant.org/)
- [ ] Use [semantic versioning](https://semver.org/) for your releases
```

<!-- Alternative approaches for a code collab session:
1. Provide people with basic practices that can help them with collaboration, like forking, pull requests and codereviews, branch management approaches.
2. Make an actual code exercise with a clear goal like for example a python module that does certain calculations and can be extended easily, and is also tested... Maybe this could be another session in the blank ones, as it sounds a bit ambitious. -->

### Assignment 1

Assume you believe to have found a bug in a library, package, or framework you are using in your project (numpy, matplotlib, pytorch, ...). This could be the first time you are thinking about contributing to an open source project. Explore what you would need to know as a (new) contributor to provide information to the developers or indeed provide a fix.

1. Think about the information you need to make a useful contribution.
2. Explore an open source project and check the information for (new) contributors.
    - What documentation do they provide?
    - How is the documentation organized?
    - What is the process of contributing to the project?
    - What tools are used to automate the process?
3. Think which tools and documentation you'd like to provide for you project needs?

:::{tip}
**💡 Tip:** Review the [Code Refinery lesson on making contributions](https://coderefinery.github.io/git-collaborative/contributing/).
:::

### Assignment 2
When collaborating with other developers, it is a good idea to define a common workflow. We recommend the Gitflow branching model as a good starting place to organize contributions to your project. This model is well suited for research software projects and allows for the incremental adoption of more control if your project warrents it.

1. Review the slides below on the Gitflow branching model

<iframe
  src="https://raw.githack.com/mwakok/FAIR4RS/main/Collaboration.html"
  style="width:100%; height:400px;"
></iframe>

*Link to slides: https://raw.githack.com/mwakok/FAIR4RS/main/Collaboration.html* 

2. Think about a contribution workflow that suits your project.

    :::{note}
    **Some questions to consider when defining a suitable workflow:**
    - What users and developers are you expecting?
    - How would you manage tracking and solving issues?
    - Does your project require a stable version to always be accessible? 
    - What instructions would you give to contributors that have modified your code and want to contribute?
    - If there are three people working together on separate features, how do you organize merging their changes?
    - Do you differentiate between internal and external developers?
    - Do all developers need equal read/write permissions?
    - Would you need to review the contributions of collaborators?
    :::

:::{admonition} **Possible next steps**
:class: dropdown
- [Protect your `main` branch](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule) if you need a stable (read-only) release to be available.
- Provide an issue template for questions, bug reporting, new features.
- Provide a pull request template.
- Use issue labels to indicate the type of issue.
:::

### Assignment 3
Document your workflow in a contributing guide called `CONTRIBUTING.md` in the root of your repository. When eager new contributors rush over to your project to make their first open source contribution, they rely on your contributor guidelines to be their guiding hand. That means that contributor guidelines should be easy to read, thorough, and friendly.

Contributing guides often cover the following situations that new contributors might face when they want to make a contribution to your project:

1. they have a question;
1. they think they may have found a bug (including unexpected behavior);
1. they want to make some kind of change to the code base (e.g. to fix a bug, to add a new feature, to update documentation);
1. they want to make a new release of the code base.

You don't need to adopt all situations, but reflect on the type of contributions your project requires.

:::{tip}
💡 Some **tips and tricks** to think about whe writing your own contributing guide:  
1. The majority of people who are reading your contributor guidelines have never contributed to your project. As such, your guidelines should be targeted at **new contributors**.
2. Recognize the fact that the reader is about to make a contribution to an open source project, which is no small feat. Let the reader know that the maintainers, other contributors, and users of the project **appreciate** this effort. This can serve as motivation for the new contributor.
3. Make sure that your contributor guidelines are **thorough**. Don't be afraid to **repeat information** that you might think is redundant. Yes, there are plenty of resources online that explain how to clone a repository or how to submit a pull request, but a new contributor might not be aware of this or want to look for it. Make sure that your contributor guidelines are the authoritative resource on how to interact with the project.
4. Keep a **light and friendly tone** in your contributor guidelines. New contributors can be nervous about contributing to a project, and a jovial tone in your contributing guidelines can help alleviate that.
:::

:::{note}
**👉 Some inspiration:**
- [Template Contributing guide](https://github.com/cncf/project-template/blob/main/CONTRIBUTING.md)
- [Example Contributing guide for TU Delft research software](https://github.com/SATAY-LL/Transposonmapper/blob/main/CONTRIBUTING.md)
- [Example Contributing guide for the TU Delft DCC Guides](https://tu-delft-dcc.github.io/community/contribute.html)
:::


### Assignment 4
Ask a colleague to review your Contributing guide and to follow the instructions to make a small contribution (ask a question, fix a typo, ... ). Update your guide if needed.

## Materials

- [Code Refinery lesson](https://coderefinery.github.io/git-collaborative/)
- [The Turing Way - Code reviewing](https://the-turing-way.netlify.app/reproducible-research/reviewing.html)
- [GitFlow original blog post by Vincent Driessen](https://nvie.com/posts/a-successful-git-branching-model/)
- [Gitflow process](http://datasift.github.io/gitflow/IntroducingGitFlow.html)

**Examples**
- [Contributing guide](https://github.com/cncf/project-template/blob/main/CONTRIBUTING.md)
- [eScience Center - matchms](https://github.com/matchms/matchms/blob/master/CONTRIBUTING.md)
