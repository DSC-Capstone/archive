---
layout: page
title: Q1 Project
doodle: /assets/images/doodle.png
---

---
* TOC
{:toc}

---

## Introduction

This quarter, each domain works through a central problem that
introduces you to the area. Depending on the domain, you will produce
either:
1. a replication of a known result in a (published) paper, or
2. an investigative paper, with a hands-on, data driven inquiry
   into a relevant question in the area.

By the end of the quarter, you will summarize the results of
your work in a well-organized report that follows the norms of
research papers in your domain.

Your work will go beyond mere paraprhasing of the existing work that
you study:
* Your domain may be taking a broader or narrower view than the work
  of any one paper. Your report will reflect the work *you* are doing,
  not the broader research that may be found in the work being
  studied.
* You will likely be using data that differs from that used in the
  work you are studying.
* Your conclusions may be different than the work you are
  studying. You should present the conclusions drawn from *your*
  data/methods and address any discrepancies with the work being
  studied.
* The code supporting your work will conform to best practices in data
  science software development.
  
## What is being turned in?

Work on the report comprises of:
1. A pdf submission of the report (w/feedback given by domain mentor),
2. The code that generates the contents of the report (w/feedback
   given by head instructor/TAs).
  
## Objectives for the Q1 report

* Carefully explaining work in your area study ensures you understand
  the area you'll be working in *very well*, details and
  all. In particular you will understand how to draw a rigorous
  conclusion in your area.
* Emulating finished work in your domain of inquiry encourages you to
  carefully consider how to effectively communicate technical ideas in
  your area.
* Critically view existing methodologies and conclusions in a way that
  raise possible improvements to existing approaches (e.g. possible
  work in Q2).
* Certain sections of your report (e.g. the literature review) will
  serve as a foundation for your writing in quarter 2.
* You will get practice using tools for producing such reports.
* Develop a library of useful code and the foundations
  of a code pipeline for further work in the area.

## Objectives for the Q1 Code

Your Q1 Project should conform to the best practices covered in
lecture. It should:
* Produce output / be runnable via a build script and targets
* Should be thoughtfully organized, using reusable library code
* Should be easily runnable in any feasable environment, for example
  on DSMLP using a docker image.
  - If your project is dependent on a specific platform, please
    inquire on Piazza, but project dependencies should be handled
    using best practices for that environment.
* Should be tested software, implementing a `test` target. This either
  leverages test data you've created (for data-driven projects) or
  unit and integration tests (for projects that create usable
  software).
  
The Q1 code will be run similarly to Methodology-HW-5.
    
    
### Code submission specifics

Turn in your code to gradescope (this will be your project
repository. In this submission, include a `submission.json`
file in the root directory of your repository that contains your
dockerhub repository (The format should be `<user>/<image>:<tag>`. The
default `<tag>` is `:latest` if you don't supply it).

```
{
    "dockerhub-id": "<user>/<image>:<tag>",
    "build-script": "<command>"
}
```

Your submission will be run on DSMLP: 
* A container will be started using the command `launch.sh -i <user>/<image>:<tag>`
 using the docker image information in `submission.json`.
* Once in the container, the 'build-script' command will be run.

For example, a `submission.json` file might look like:
```
{
    "dockerhub-id": "amfraenkel/fair-policing-project",
    "build-script": "python run.py"
}
```

And the following commands would be run on DSMLP:
* `launch.sh -i amfraenkel/fair-policing-project`
* `cp <project> .`
* `cd <project>`
* `python run.py test`

Where `<project>` is the code that's been turned into Gradescope.


*Note:* This assignment should readily apply to all domains. 
* Data-centered domains start with collected data (that you will model
  your test data after).
* Methods domains are building algorithms that take data as input. You
  should choose a data type that your algorithm may input and use that
  to model your test data.
