# Week 5 - Reproducibility

:::{admonition} Today's learning objectives
**Topics for today**
- Set up a reproducible computing environment
- Get feedback on environment reproducibility

**What to expect**
After going through the assignments, you will have reproduced someone else's environment.
:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](/isBPjSUoRL6Kvr1LjaZe7Q)
- Discuss previous assignments and share progress [10 min]
- Introduce challenge and explain assignments [15 min]
- Work on assignments [90 min]

## 🙋 Discussion and questions
👉 Go to [**collaborative document**](https://hackmd.io/@fair4rs/ryvq65tZ3).


## Assignments for Friday 21st of April

The goal of the this week's challenges and assignments is to make sure your project is reproducible. The best test is to get someone to reproduce your computational environment.

In order have a reproducible computational environment certain things need to be in place including, dependency documentation, basic instructions for the users. Some setups may include running tests or providing examples to reproduce. Today we would like to help you find out and define also what specific considerations should be taken into account for your project.

*Consider adding the FAIR card below as an issue in your project board for future reference.*

### Getting started with the essentials
:::{tip}
Tip: Add the FAIR card to your github board to keep practicing project management tools.
:::
**FAIR card: Dependency management**
```markdown
_Essential_
- [ ] Document your project dependencies
- [ ] Provide instructions for replicating the computational environment

_Recommended_
- [ ] Use a [dependency manager](https://the-turing-way.netlify.app/reproducible-research/renv/renv-package.html)
- [ ] Pin [exact versions](https://github.com/conda/conda-lock) used to generate your environment

_Optional_
- [ ] [Containerized workflow](https://the-turing-way.netlify.app/reproducible-research/renv/renv-containers.html)
```
### Some examples to get inspired
**Python example using containerized solution**
- TU Delft: https://github.com/SATAY-LL/Transposonmapper
- eScience Center: https://github.com/matchms/matchms

**Cpp reproducible example:** 
- Bitbucket: https://bitbucket.org/EmirD/murtree/src/master/
- Github: https://github.com/MurTree/murtree

**Low end project example, not meant to be maintained but still reproducible:**  
- https://github.com/jurra/articles_scraper

### Assignment 1
1. Think about what defines your computational environment:

    - *Hardware requirements (GPU, CPU cores, memory)*
    - *Operating system*
    - *Third-party (proprietary) software* 
    - *Programming language*
    - *Packages and libraries (and their versions)*
    - *Local relative folder structure*

2. Choose the most appropriate method for your project for capturing your computational environment and create a dependency file. 
    - *How tightly do you need to control the version of the dependencies?*

:::{tip}
**💡 Tips:**
- While [**Conda**](https://the-turing-way.netlify.app/reproducible-research/renv/renv-package.html) is Python-centric to a degree, it is also well-integrated for use with other languages. For example, the base version of Conda includes the [**C++ standard library**](https://www.prouvost.dev/post/2021/c-development-with-conda/).
- Does your conda take a long time to resolve the dependencies? Have a look at [**mamba**](https://mamba.readthedocs.io/en/latest/)!
- Matlab toolbox requirements can be found with this [**function**](https://nl.mathworks.com/help/matlab/ref/matlab.codetools.requiredfilesandproducts.html) or with the [**Dependency Analyzer**](https://nl.mathworks.com/help/matlab/matlab_prog/analyze-project-dependencies.html).
- For complex dependencies or strict OS requirements, it might be easier to create a snapshot of the entire computing environment including the OS and all dependencies using a [**container**](https://the-turing-way.netlify.app/reproducible-research/renv/renv-containers.html).
:::

 
### Assignment 2
Get someone to test your project's reproducibility. In order to achieve this milestone, consider the following questions:
- _What is my user's background and level?_
- _What is an acceptable minimum time to reproduce your environment?_
- _How do you know the environment is successfully recreated?_

1. Brainstorm and write down the steps and checkpoints you need to consider to achieve the above for your project.
2. Make any modifications (commit) in your repo during the process including the feedback you get from someone that tried to reproduce your environment.


:::{adminition} Read this if you get stuck
:class: dropdown
- Document the steps to recreate the computational environment in your `README.md`
- Share your installation instructions with a colleague and invite she/him to install and test your environment.
- Get feedback.
:::

:::{tip}
**Don't forget to:**
- Share progress in our channel
- Use your journal to collect notes, links and progress that can be used to showcase progress and celebrate it
:::

## Materials
**Reproducible environments**
- [Code Refinery lesson](https://coderefinery.github.io/reproducible-research/)
- [The Turing Way - Reproducible environments](https://the-turing-way.netlify.app/reproducible-research/renv.html)
- [Conda cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdfs)
- [Faster conda alternative: Mamba](https://mamba.readthedocs.io/en/latest/)
- [Pin exact versions with conda-lock](https://github.com/conda/conda-lock)

**Containers**
- [Introduction to Docker containers](https://carpentries-incubator.github.io/docker-introduction/)
- [The Turing Way - containerized workflow](https://the-turing-way.netlify.app/reproducible-research/renv/renv-containers.html)
- [Ditching Docker Hub: serve research software with GHCR + Zenodo](https://blog.esciencecenter.nl/ditching-docker-hub-serve-research-software-with-ghcr-zenodo-2e47b8c93d88)

**Matlab**
- [Find your Matlab dependencies](https://nl.mathworks.com/help/matlab/ref/matlab.codetools.requiredfilesandproducts.html)
- [Matlab Dependency Analyzer](https://nl.mathworks.com/help/matlab/matlab_prog/analyze-project-dependencies.html)
