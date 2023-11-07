# Week 4 - Project planning

:::{admonition} Today's learning objectives
**Topics for today:**
- Reflect on the status of your project with respect to the Code Refinery lessons
- Define your project goals
- Introduce project planning with GitHub project boards

**What to expect**  
By the end of this seminar and by completing the assignments, you will put your project under version control, upload it to GitHub, and create a roadmap with actionable steps using issues and a project board.
:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](./code-of-conduct.md)
- Reflect on the Code Refinery and upcoming seminars [10 min]
- Discuss previous assignments [10 min]
- Introduce project boards [15 min]
- Introduce assingments [15 min]
- Work on assignments [50 min]


## 🙋 Discussion and questions
👉 Go to [**collaborative document**](https://hackmd.io/gFcSU_F9SpuHrxomZTSVTQ?both).


## Introduction to project planning 
If you plan a large piece of work in your project, it is a good idea to produce an outline of the work. Your roadmap should cover your goal and vision and include a timeline for tasks that need to be completed, thus helping yourself and your collaborators to get an understanding of what is currently happening on the project and what’s coming next.

To create a roadmap, it is important to map out the key milestones, tasks needed to accomplish the milestones and related challenges to help you allocate your resources and time to work on them efficiently. 

### Creating a roadmap
Write a simple roadmap composed of milestones. You can use this draft roadmap to translate the requirements/considerations captured in your SMP into more actionable information.
1. Draft your first roadmap in your FAIR journal.

:::{tip}
- Use the insights you have captured in your SMP template to identify milestones
- If you would like to get feedback on your roadmap, you can share it as issue in your repository.
- Consider all kinds of aspects that are relevant to your project from writing code to publishing and training.
:::

**Example of milestones for a roadmap:**
```
## Roadmap milestones
- Refactor my codebase and add integration and unit tests 
- Create a website with documentation, contribution guidelines, and tutorials
- Make my codebase available to students in an upcoming course
- Release a first prototype that can be tested by (external) colleagues by mid 2023
- Optimize my code for execution on an cluster
- Publish paper by end 2023
```

## Assignments for Friday 14th of April

**Prerequisites:**
:::{warning}
- [ ] Check that everyone can follow the program on Github.
- [ ] We recommend to first create a **private repostory** that you will subsequently prepare for publishing during the program.
- [ ] Check that there are no major issues in making your project public. 
    - Are there any privacy or confidentiality concerns in your project?
    - Do you need a particular license?
    - Are there obstacles that may not allow you to make it open for FAIR and open science?
:::

### Follow along demo: How to use github boards
We will demonstrate and discuss how to use GitHub project board to planning and organizing your project. Have a look how others are using project boards on GitHub: [xarray](https://github.com/pydata/xarray), [matplotlib](https://github.com/matplotlib/matplotlib).

:::{admonition} Instructor notes
:class: dropdown

- Tools integrated to project management:
    - Github boards. Brief comment on Kanban and different styles.
    - Milestones, issues, notes, tasks
    - Pull requests and reviews
    - Roles and assignment of tasks
    - Roadmaps
- Showcase a minimum GitHub planning workflow.
- Discuss a more advanced scenario.
:::


### Assignment 1
1. Create your private project repository on GitHub
2. Create a project board
3. Create a new issue using the **FAIR card** below and add it to the ToDo column.

:::{tip}
During each seminar, we will share a **FAIR card** with essential and recommended practices for the topic.
:::
 

**FAIR card: Version control**
```markdown
_Essential_  
- [ ] Use [git](https://www.atlassian.com/git) as a version control system 
- [ ] Upload your project on [GitHub](https://github.com/) or [TU Delft GitLab](https://gitlab.tudelft.nl/)

_Recommended_  
- [ ] Make your repository [public](https://coderefinery.github.io/social-coding/)
- [ ] [Branch hygiene](https://coderefinery.github.io/git-branch-design/)
- [ ] [Meaningful commit messages](https://www.git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project#_commit_guidelines)
```

### Assignment 2
1. Populate your board with your project goals in the form of issues/notes.
    - Define your milestones in GitHub
    - Add issues to your milestones
    - Add the issues to your project board
    - Consider creating task lists in your issue

:::{note}
**Things to consider**
- Modify your github board to reflect a workflow that matches the level of complexity of your project.
- How will you differentiate between an idea, bug, task, or feature? What labels will you use?
- If you are collaborating, how will issues be assigned?
:::

### Assignment 3 
_For those who don't have their project on Github_

1. Prepare your project for pushing to GitHub
    - Create a local repository
    - Which files will you track?
    - Which files will need to be ignored (see .gitignore)?
2. Push your local repository to GitHub


## Materials
**Git**
- [Code Refinery Git lesson](https://coderefinery.github.io/git-intro/)
- [Pro Git book](https://git-scm.com/book/en/v2)
- [DCC Guides - Branch management](https://tu-delft-dcc.github.io/software/git/branch_management.html)
- [The Turing Way - Version control for data](https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-data.html)
- [Templates for .gitignore](https://github.com/github/gitignore)

**Project planning**
- [GitHub boards](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/managing-project-boards/about-project-boards)
- [Build Better Scientific Software - Better Planning blogs](https://bssw.io/items?category=better-planning)

**Licenses**
- [TU Delft - Research Software Policy](https://zenodo.org/record/4629662#.ZCwWVnZBzuo)
- [The Turing Way - Software Licenses](https://the-turing-way.netlify.app/reproducible-research/licensing/licensing-software.html)