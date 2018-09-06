---
layout: post
title: Reverse-engineering Configuration Constraints
date: 2016-10-26 16:37:00
permalink: /smr/config-constraints/
group: research
tags: completed
weight: 1
---

One of the challenges of developing and maintaining highly configurable software is reasoning about configuration constraints (aka feature dependencies). For example, some features do not work well together or some features require other features to be present. These constraints are essential for reasoning about valid configurations of the software, but unfortunately are not always documented. In this project, we develop a framework that analyzes the implementation of existing highly configurable software to identify configuration constraints.<!--more--> We make use of TypeChef's variability-aware analysis to analyze several variants of the program at once. Our analysis is based on two rules. Rule 1 detects any conditional build-time errors (e.g., type and linker errors). Rule 2 is a novel approach that globally checks under which condition a feature changes the compiled code. We conduct an empirical study on four large open-source software systems (uClibc, eCos, Linux, and Busybox). Our analysis is highly accurate for both rules (93% and 77% respectively) and can recover 28% of the existing variability model constraints.

We also conduct a qualitative study to understand the sources of the remaining constraints. This was by manually analyzing the non-recovered constraints, interviewing 27 developers through phone interviews and online questionnaires, as well as additional automated analysis that counts certain phenomenon. By analyzing the data from these different sources, we find that configuration constraints are enforced mainly for four reasons: (1) enforcing low-level code dependencies, (2) ensuring correct run-time behavior, (3) improving the user’s configuration experience, and (4) preventing corner cases. The classification suggests that while automated tools can potentially extract almost half of the enforced configuration constraints, other constraints require testing or domain knowledge limiting the completeness of automated tools.

Read the full details in our [ICSE '14](/resources/pubs/NADI_ICSE14.pdf) and [TSE'15](/resources/pubs/NADI_TSE_2015.pdf) papers.

Additional information about our tools and data can be found in our [online appendix](http://gsd.uwaterloo.ca/farce).


