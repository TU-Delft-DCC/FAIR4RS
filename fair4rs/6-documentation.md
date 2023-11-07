# Week 6 - Documentation

:::{admonition} Today's learning objectives
**Topics for today:**
- Understand the different types of documentation relevant to software projects
- Start using essential documentation best practices
- Review the readability of your code

**What to expect**
By the end of the seminar we would like you to have a documentation approach/system that fits your project requirements. 

:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](./code-of-conduct.md)
- Discuss previous assignments [20 min]
- Introduce assignments [15 min]
- Work on assignments [50 min]

## 🙋 Discussion and questions
- Reflect on the fact that preparing a repo to become reproducible is already a documentation exercise. 
    - You have already started working on dependency documentation and installation instructions.
    - Some have tests and notebook examples.
    - Readable code is documentation.
    
:::{warning}
**Some statements to provoke discussion:**
- Documentation is everything
    - *What do you think is the main documentation source in a codebase?*
- Code is for computer, comments are for humans.
    - *What is the role of comments in your code?*
- Readable code is sufficient for good code documentation.
    - *Who should be reading your code?*
- Different users approach your code differently. 
    - *Can you think of different users and usecases?*
    - *Which documentation tools would you use?*
:::


👉 Go to [**collaborative document**](https://hackmd.io/@fair4rs/rJoEhe4zn).


## Assignments for Wednesday 26th of April
The goal of the this week's challenges and assignments is to find a documentation system/approach that works for your project specific needs.

:::{tip}
**💡 Tip:** Add the FAIR cards to your github board to as a reference for FAIR documentation.
:::

### FAIR card - Project documentation
```markdown
_Essential_  
- [ ] [README](https://github.com/18F/open-source-guide/blob/18f-pages/pages/making-readmes-readable.md)
- [ ] [LICENSE](https://doi.org/10.5281/zenodo.4629662)
- [ ] [CITATION](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-citation-files)

_Recommended_  
- [ ] Make use of [Github issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)
- [ ] [Code of conduct](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-code-of-conduct-to-your-project)
```

### FAIR card - Software documentation
```markdown
_Essential_  
- [ ] Installation instructions
- [ ] User documentation
- [ ] Developer documentation
- [ ] Source code documentation ([docstrings](https://numpydoc.readthedocs.io/en/latest/format.html))

_Recommended_  
- [ ] Examples and tutorials (Jupyter notebooks, videos, screencasts)
- [ ] Automate documentation building with [sphinx](https://coderefinery.github.io/sphinx-lesson/)
- [ ] Website ([github.io pages](https://pages.github.com/), [Readthedocs](https://readthedocs.org/), [JupyterBook](https://jupyterbook.org/intro.html)

_Optional_  
- [ ] Build [API reference](https://developer.lsst.io/python/numpydoc.html) from docstrings
```


### Assignment 1 
Add essential files that make your software project instantly more Accessible and Reusable:
1. LICENSE file
    
    The TU Delft released a high-level [Software Policy](https://zenodo.org/record/4629662#.ZD7vJnZByUk) that lists pre-approved open-source licenses. 
    
    :::{note}
    For more information, detailed [TU Delft Research Software Guidelines](https://d2k0ddhflgrk1i.cloudfront.net/TUDelft/Over_TU_Delft/Strategie/TU%20Delft%20Research%20Software%20Guidelines.pdf) about licensing, registration, and commercialization are available. This document also details the required steps to reclaim the copyright to your software (page 27) as TU Delft by default holds the rights to the software created by its employees.
    :::
   
:::{tip}
**💡 Tip:** Licenses simplified by [Choose a license](https://choosealicense.com/licenses/) and [Software licenses in plain English](https://www.tldrlegal.com/)
:::

2. CITATION.cff file
    
    You can add a [CITATION.cff](https://citation-file-format.github.io/) file to the root of a repository to let others know how you would like them to cite your work. The citation file format is plain text with human- and machine-readable citation information. More information and compatible tools can be found in this [repository](https://github.com/citation-file-format/citation-file-format). 

### Assignment 2
Now that we have the minimum required for FAIR documentation for research software, let's define a broader approach towards your project documentation.

:::{note}
**What do we mean by documentation system?**

What no body tells you about documentation is that is not just one thing, but several. How-to-guides, tutorials, in-code documentation, knowledge-base and explanation of concepts can all be part of documentation. In the case of research software, Jupyter notebooks often are an essential documentation tool. [**Divio**](https://documentation.divio.com/) offers a great overview of the types of documentation.
:::

1. Define the documentation that you, your users, and your collaborators would need to understand and use your software.
2. Make a todo list (GitHub issues) based on these considerations.

:::{tip}
**💡 Tip:** Think about a minimum approach that improves your current situation, and a more ambitious approach.
:::

### Assignment 3
[Readable code](https://raw.githack.com/mwakok/FAIR4RS/main/Readability.html) and [in-code documentation](https://coderefinery.github.io/documentation/in-code-documentation/) are important parts in making your code easy to understand To improve the readability of your code, you should consider:

- Writing code comments that explain the **why** of the code and not the **what**.
- Adding docstrings to (public) functions.
- Using common naming conventions (check a style guide).
- Adding whitelines and avoid compound statements.

:::{note}
Every major open-source project (e.g. [**Numpy**](https://numpydoc.readthedocs.io/en/latest/format.html)) has its own style guide: a set of conventions (sometimes arbitrary) about how to write code for that project. It is much easier to understand a large codebase when all the code in it is in a consistent style. 
:::

1. Checkout a style guide for your Programming language and review your code for the readability considerations listed above.
    - Would it make sense to adopt a style guide for your project?
    - What conventions do you find useful?

2. Following style guides can be made easy with a [linter](https://github.com/caramelomartins/awesome-linters). Review your code by running a linter (e.g. `flake8` for Python, `checkcode` for MATLAB, `IntelliSense`for C++, or `lintr` for R) to identify conflicts with the style guide.

3. Make a todo list (GitHub issues) to improve the readability of your code. 

:::{tip}
**💡 Tip:**
For Python, the recommended docstring styles are the [Numpy](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_numpy.html) and [Google](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html#example-google) styles. Both can be interpreted by sphinx.
:::

### 💪 Extra (optional) Assignments
- Build your documentation with sphinx
    - Check the [Code Refinery lesson](https://coderefinery.github.io/documentation/sphinx/)
- Deploy your documentation to GitHub pages.
    - Check the [Code Refinery lesson](https://coderefinery.github.io/documentation/gh_workflow/)

## Materials

- [Code Refinery lesson](https://coderefinery.github.io/documentation/)
- [Quarto](https://quarto.org/)
- [Myst parser](https://myst-parser.readthedocs.io/en/latest/)
- [TU Delft Research Software Policy](https://zenodo.org/record/4629662#.ZD7vJnZByUk)
- [TU Delft Guidelines on Research Software](https://d2k0ddhflgrk1i.cloudfront.net/TUDelft/Over_TU_Delft/Strategie/TU%20Delft%20Research%20Software%20Guidelines.pdf)
- [CITATION.cff reference](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md)

**Sphinx**
- [Theme gallery](https://sphinx-themes.org/)
- [Jupyerbook](https://jupyterbook.org/en/stable/intro.html)
