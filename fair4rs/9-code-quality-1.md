# Week 9 - Code Quality I

:::{admonition} Today's learning objectives
**Topics for today:**
- Concepts of code quality
- Assessing code quality
- Understand the process of refactoring 
- Write a first test


**What to expect**
By the end of the seminar we would like you to have identified possible improvements in the quality of your software and started writing a test.
:::

## 📆 Seminar schedule

- Welcome!
- Reminder of the [**Code of Conduct**](/isBPjSUoRL6Kvr1LjaZe7Q)
- Discuss previous assignments [10 min]
- Reflection on software quality [45 min]
- Introduce assignments [5 min]
- Work on assignments [50 min]

## 🙋 Discussion and questions


## Reflection on software quality

The [FAIR principles for research software](https://www.nature.com/articles/s41597-022-01710-x) do not provide a set of best practices that ensure a minimum level of code quality. Closest comes the **Reusable** section, which states that *software is both usable (can be executed) and reusable (can be understood, modified, built upon, or incorporated into other software)*, with the subcriteria **R3**: *Software meets domain-relevant community standards*. 

:::{warning}
**Questions:** 
- What would you consider clean and quality code?
- What would you consider bad code?
:::

Writing good quality and clean code ensures that your software is easy to understand, maintain, extend, and reuse. The Code Refinery introduced a couple of practical lessons to improve and maintain the quality of code by
- Writing **modular code** with **small** and **pure functions**
- Writing readable code by following **style guides** (see also [**Week 6**](https://hackmd.io/wQ_mlHUqSeSDPLPKh2Fsqg#Assignment-3))
- Using **defensive** programming
- Writing (automated) **tests**

In addition, we would add **error handling** for code robustness and **logging** for code debugging.

:::{tip}
**A good example:**
Example of research software from the eScience Center that implements code quality checks: **https://github.com/matchms/matchms**.
:::


:::{info}
**Additional information**
The University of Utrecht has offered a module on Code Quality during a workshop on software reproducibility. Have a look at the slides for some general tips and common best practices:

<iframe
  src="https://utrechtuniversity.github.io/workshop-computational-reproducibility/slides/slides_code-quality.html#1"
  style="width:100%; height:400px;"
></iframe>

---
We identified three additional resources that provide some standards on code quality criteria and best practices for (research) software:
1. The [OpenSSF Best Practices Badge Program](https://bestpractices.coreinfrastructure.org/en) offers a shared quality standard for open software. Projects can voluntarily self-certify, at no cost, by using a web application to explain how they follow each of the [**best practices**](https://bestpractices.coreinfrastructure.org/en/criteria/0). Once completed, you are provided with a badge to add to your repository.
2. The European Open Science Cloud (EOSC) Association has created [tools and documentation](https://www.eosc-synergy.eu/for-developers/) for setting software quality standards for research. They have developed a [**minimum viable set of quality requirements**](https://digital.csic.es/bitstream/10261/160086/11/manuscript-v4.1.pdf) for software.
3. The International Standard Organisation (ISO) has issued a standard (ISO 9126) for software quality criteria (not specific to research software). An overview of the standard with descriptions, can be found [**here**](https://www2.cs.sfu.ca/~cameron/Teaching/473/quality_characteristics.html).
    :::spoiler Diagram
    ![ISO 9126](https://hackmd.io/_uploads/S1Q181tV2.png =500x500)
    :::
:::

## Assignments for Wednesday 17th of May
The goal of the this week's challenges and assignments is to identify ways to improve the quality of your code and start with refactoring and testing a small part.


:::{tip}
**💡 Tip:** Add the FAIR card to your Github board to as a reference on writing tests for research software.
:::

### FAIR card - Testing
```markdown
_Essential_
- [ ] Document how users can verify the proper functioning of the software
- [ ] Document verification for user installation and software execution

_Recommended_  
- [ ] [Defensive programming](https://swcarpentry.github.io/python-novice-inflammation/10-defensive/index.html)
- [ ] Test your software with [integration tests](https://the-turing-way.netlify.app/reproducible-research/testing/testing-integrationtest.html) and [unit tests](https://the-turing-way.netlify.app/reproducible-research/testing/testing-unittest.html)
- [ ] Make use of [Continuous Integration](https://the-turing-way.netlify.app/reproducible-research/ci/ci-options.html)
- [ ] Code coverage check ([Codecov](https://about.codecov.io/), [Sonarcloud](https://sonarcloud.io/), [Travis](https://www.travis-ci.com/)).
- [ ] Ensure a minimum test coverage of 70%.
```

---
### Assignment 1
We will conduct a code review together and assess a software project for possible improvements in code quality. 

Example repo: https://github.com/anailil/FAIR-well-logs
Context about the project: https://anailil.github.io/Quick-Visualisation-of-Geophysical-Borehole-Data/

From the [ISO standard for software criteria](https://www2.cs.sfu.ca/~cameron/Teaching/473/quality_characteristics.html), let's review the code with a focus on the following criteria:

- Accuracy: Does the code provide the right or agreed-upon results or effects?
- Maturity: Are inputs and types checked?
- Resource Utilization: How does the performance scale with the dataset size?
- Analyzability: How are errors and exceptions handled?
- Changeability: How easy is it to extend the code with new features? 
- Stability: How easy is it to make changes? 
- Testability: How can the code be tested?

In addition, here a some **code smells** to look out for:

:::{important}
- Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
- Fragility. The software breaks in many places due to a single change.
- Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
- Needless Complexity.
- Needless Repetition.
- Opacity. The code is hard to understand.
:::

:::{tip}
💡 Many books, articles, and blogs have been written about clean code. For a succinct list, we like [**The Zen of Python**](https://peps.python.org/pep-0020/) and a summary of [**Uncle Bob's book on clean code**](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29). The Turing Way also provides a good [**checklist for a Code Review**](https://the-turing-way.netlify.app/reproducible-research/reviewing/reviewing-checklist.html).
:::

---
### Assignment 2
Now, evaluate your own project following the software quality characteristics we discussed in Assignment 1. 

- Read the following content on software quality: https://www2.cs.sfu.ca/~cameron/Teaching/473/quality_characteristics.html
- Make a list of quality "subcharacteristics" as described in the article you feel are relevant in the current phase of your project.
- Consider for these priorities those things you will address in your next release.

Here is an example to help you get started:
:::{info}
**Must address this year**
- Suitability: The capability of the software to provide an adequate set of functions for specified tasks and user objectives. 
- ...

**Should address this year**
- Resource Utilization: The capability of the software to use appropriate resources in an appropriate time when the software performs its function under stated condition.
- ...

**Could address if I get feedback from users/developers**
- Changeability: The capability of the software product to enable a specified modification to be implemented.
- ...

**Won't address for now**
- Time Behavior: The capability of the software to provide appropriate response and processing times and throughput rates when performing its function under stated conditions.
- ...
:::

:::{tip}
**💡 Tip:** You can be more specific by defining specific tasks and objectives. Or revisit your project features backlog and reuse what you have written there. 
:::

---
### Assignment 3
:::{info}
**Code refactoring**  
In computer programming and software design, code refactoring is the process of restructuring existing computer code — changing the factoring — without changing its external behavior. Refactoring is intended to improve the design, structure, and/or implementation of the software (its non-functional attributes), while preserving its functionality. 
:::

Refactoring is often an ongoing process to improve your code. In order to refactor a piece of code and ensure that its functionality and external behaviour won't change, we can make use of tests. A good approach to follow:

1. Identify a small piece of code you want to improve.
2. Ensure the code is in the form of a small function (or class method).
3. Add (or update) tests that define the expected behaviour of the function.
4. Verify the passing of the tests.
5. Refactor the function to improve the quality.
6. Verify the passing of the tests.

This process is a good strategy to slowly improve the coverage of your code with tests. Each time you refactor a piece of code, add a test that captures the correct behaviour. Follow the Boy Scouts rule: *Leave the campground cleaner than you found it*.

:::{tip}
**💡 Tips:** 
- Review the [**Code Refinery lesson**](https://coderefinery.github.io/testing/) on testing
- [**Link**](https://refactoring.guru/refactoring/what-is-refactoring) to tips about the process of refactoring
- [**Code refactoring**](https://www.freecodecamp.org/news/best-practices-for-refactoring-code/) best practices for Python
- Examples of [**bad code**](https://www.reddit.com/r/badcode/)
- Bad code to better code, [**an example**](https://levelup.gitconnected.com/bad-code-to-better-code-an-example-5fe034f448f6).
:::


## Materials

### Code quality
- [The Turing Way - code quality](https://the-turing-way.netlify.app/reproducible-research/code-quality.html)
- [Code Refinery lesson on modular code](https://coderefinery.github.io/modular-type-along/)
- [EOSC documentation](https://www.eosc-synergy.eu/for-developers/)
- [OpenSSF Best Practices Badge](https://bestpractices.coreinfrastructure.org/en)
- [Utrecht University - Code quality](https://utrechtuniversity.github.io/workshop-computational-reproducibility/slides/slides_code-quality.html#1)
- [Clean code by Uncle Bob](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)

### Testing
- [Code Refinery lesson on testing](https://coderefinery.github.io/testing/)
- [The Turing Way - testing](https://the-turing-way.netlify.app/reproducible-research/testing.html)

### Reviewing code
- [The Turing Way - Code reviewing process](https://the-turing-way.netlify.app/reproducible-research/reviewing.html)
- [Example of a review process](https://www.youtube.com/watch?v=Kxxr1UdXTmI)

### Refactoring
- [Best practices for refactoring code for Python](https://www.freecodecamp.org/news/best-practices-for-refactoring-code/)
- [What is refactoring](https://refactoring.guru/refactoring/what-is-refactoring)
