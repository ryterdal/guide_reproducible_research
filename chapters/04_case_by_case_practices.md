Case-by-case Practices
======================

:::{attention}
This chapter is still a work-in-progress. Check back when you've got some
experience with research computing and are ready to learn more.
:::

This chapter covers case-by-case practices for reproducibility. Many of these
practices require substantial effort to adopt or require specific technical
knowledge. They can be important and even essential for certain kinds of
projects, but we feel they aren't broadly applicable in the ways that primary
and secondary practices are. DataLab occasionally adopts these practices. Read
this chapter when you feel like you've mastered the practices in the previous
chapters and want to learn even more.



Documentation
-------------

### Make Workflow Diagrams

:::{seealso}
See DataLab's [README, Write Me! workshop reader][datalab-readme] for
suggestions about how to create workflow diagrams.
:::

[datalab-readme]: https://ucdavisdatalab.github.io/workshop_how-to-data-documentation/#workflow-diagrams


### Use Issue Tracking


### Make a Data Management Plan

:::{seealso}
See DataLab's [Data Management Plan toolkit][datalab-dmp] for instructions
about how to make a data management plan.
:::

[datalab-dmp]: https://datalab.ucdavis.edu/data-management-plans/


Artifact Preservation
---------------------

### Log Output

:::{seealso}
If you're using R, see DataLab's [Intermediate R: Outputs, Errors, and Bugs
workshop reader][datalab-r-output] for a brief overview of a how to manage log
files in R.

If you're using Python, see DataLab's [Intermediate Python: Squashing Bugs with
Python's Debugging Tools workshop reader][datalab-py-output] for a brief
overview of how to manage log files in Python.
:::

[datalab-r-output]: https://ucdavisdatalab.github.io/workshop_intermediate_r/output-errors-and-bugs.html#logging-output
[datalab-py-output]: https://ucdavisdatalab.github.io/workshop_intermediate_python/chapters/04_debugging.html#logging


### Use Version Control for Data




Project Organization
--------------------

### Make a Package


Workflow Automation
-------------------

```{figure} /images/xkcd_is_it_worth_the_time.png
---
name: xkcd-worth
alt:
---
"Is It Worth the Time?" from ["xkcd"][xkcd] by Randall Munroe
([license][xkcd-license]).
```

[xkcd]: https://xkcd.com/
[xkcd-license]: https://xkcd.com/license.html



### Use a Build System

:::{seealso}
See DataLab's and DIB Lab's [Automating Your Analyses with the Snakemake
Workflow System workshop reader][datalab-snakemake] for a technical
introduction to snakemake.
:::

[datalab-snakemake]: https://ngs-docs.github.io/2021-august-remote-computing/automating-your-analyses-with-the-snakemake-workflow-system.html


### Use Integration Tests

#### On Unit Tests

### Use Continuous Integration

#### Lint the Code

#### GitHub Actions


Environment Management
----------------------

### Use an Environment Manager

A **computing environment** is a collection of hardware and software used to
run computations. Whether a computation runs correctly or at all depends on the
computing environment, so an important part of making a project reproducible is
documenting the environment where the code was originally developed and tested.

In high-level programming languages like R and Python, details of the hardware
are mostly hidden away. That is, hardware has little to no impact on how you
write code, with only a few exceptions. Hardware may affect how quickly your
code runs, but usually not the final result. As a consequence, for many
research computing projects, the hardware environment is of less concern than
the software environment.

One of the major advantages of the open-source and open-science ecosystem is
the trove of packages and other software developed and published by members of
the community. As these are updated, projects that rely on older versions may
cease to work correctly unless they are also updated. So for most projects,
keeping track of the software environment means keeping track of the specific
versions of packages and other software with which the project was carried out.

A **virtual environment** is a computing environment with specific software
versions that can coexist alongside other virtual environments with different
software versions. An **environment manager** is a software tool that can
create virtual environments. Environment managers can usually also install,
update, and remove software.

```{figure} /images/xkcd_python_environment.png
---
name: xkcd-python
alt:
---
"Python Environment" from ["xkcd"][xkcd] by Randall Munroe
([license][xkcd-license]).
```

Many different open-source environment managers exist. Among those explicitly
designed for research computing, [conda][] is the de facto standard. Conda was
originally developed to manage Python environments, but now supports other
languages such as R and Julia.

[conda]: https://docs.conda.io/

:::{tip}
A relatively new package manager, [Pixi][], is faster and is better at
accurately reproducing environments than conda, while maintaining compatibility
with conda packages. Pixi also provides several other features that make it
pleasant to use. At DataLab, we are just starting to switch over to Pixi.

[Pixi]: https://pixi.sh/
:::

:::{note}
If you exclusively use R and prefer to use an environment manager developed
specifically for R, check out the [renv][] package.

[renv]: https://rstudio.github.io/renv/
:::

By using an environment manager like conda, you can ensure that the versions of
packages and software your projects depend on are recorded. Generally you
should create a new virtual environment for each project, and switch between
them as needed. Environment managers provide tools to save a description of a
virtual environment to a file and to recreate an environment from such a file.
This way you and your collaborators can set up a project on a new computer and
make sure it has the correct software environment.


:::{seealso}
See [the Setting Up Software chapter][datalab-micromamba] in DataLab's
Introduction to Remote Computing workshop reader for a technical introduction
to micromamba, a fast and efficient drop-in replacement for conda.

If you prefer to use the original conda, instead see DataLab's [Making Python
Projects & Environments Reproducible workshop reader][datalab-conda]. Then see
DataLab's and DIB Lab's [Installing Software on Remote Computers with Conda
workshop reader][datalab-conda-remote] for even more technical details.
:::

[datalab-micromamba]: https://ucdavisdatalab.github.io/workshop_intro_to_remote_computing/chapters/02_environment-setup.html
[datalab-conda]: https://ucdavisdatalab.github.io/workshop_intermediate_python/chapters/02_reproducible.html
[datalab-conda-remote]: https://ngs-docs.github.io/2021-august-remote-computing/installing-software-on-remote-computers-with-conda.html


### Use Virtualization

#### Containers

#### Virtual Machines

### Go to the Cloud


