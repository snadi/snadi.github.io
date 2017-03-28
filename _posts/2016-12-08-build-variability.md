---
layout: post
title: Analyzing Linux Kbuild to Detect Variability Anomalies
permalink: /kbuildvariability/
group: research
tags: completed
weight: 2
---

Although build systems control what code gets compiled into the final built product, they are often overlooked when studying software variability. The Linux kernel is one of the biggest open source software systems supporting variability and contains over 10,000 configurable features described in its KCONFIG files. To understand the role of the build system in variability implementation, we use Linux as a case study. We study its build system, KBUILD, and extract the variability constraints in its Makefiles.<!--more--> We show that almost 50% of the configurable features in Linux control the compilation of code files in the build system. We use the extracted constraints to detect variability anomalies in the form of dead and undead code files and code blocks. You can find the full details in our [WCRE'11](/resources/pubs/NADI_WCRE2011.pdf), [CSMR'12](/resources/pubs/NADI_CSMR2012.pdf), and [JSEP '13](/resources/pubs/NADI_JSEP_2013.pdf) papers.

In the WCRE paper, we first start with looking at the syntax of conditionally compiling files in Kbuild and ensure that all files have a chance to get compiled. We develop three rules to identify variability anomalies due to problems within Kbuild.

We then investigate the variability in Kbuild in more details in the CSMR paper. We implement a tool which reads the Makefiles, and extracts the relevant variability constraints. These are the presence conditions under which each file will compile. We use this information to detect additional variability anomalies in Linux, and show that the build information is needed to accurately detect anomalies.

In the JSEP paper, which is an extension of our CSMR paper, we enhance our constraint extractor and call it Makex. Makex is implemented in Java, and has a current source file coverage rate of 85%. Since this is a text based parsing, and Kbuild notation is exteremely complicated, there are still some limitations which we will try to address. Makex has been tested on releases 2.6.30 - 3.6, but is not guaranteed to run correctly on older/newer versions.

This is the latest version of Makex: [Makex](/resources/kbuild/LinuxMakeFileParser) (referred to as Linux Makefile Parser in the CSMR paper). You can also find the source code [here](https://bitbucket.org/snadi/makex).


To run it, run the following command from within a Linux tree:

```
java -classpath LinuxMakeFileParser.jar -Xms1024M -Xmx2048M makefiles.Makex
```


The constraints in Kbuild will be outputted in a "models" directory, with one .makemodel file for each Linux architecture present. Files which are compiled unconditionally will have no constraints.

In order to identify tristate features, we rely on the kconfig models extracted by [Undertaker](http://vamos.informatik.uni-erlangen.de/trac/undertaker). We basically need the list of features (i.e., which also have a _MODULE variation) defined as tristate in the Kconfig files. A list of such features for releases 2.6.34-3.6 is available [here](/resources/kbuild/module-items.zip). Add the modules.txt file to your work directory before running Makex. You can simply add an empty modules.txt file, but no _MODULE variation will be generated in the make constraints which may lead to false positives.

You can use [this](/resources/kbuild/undertakerAnalysis) script as an example of how to run the analysis to detect dead and undead blocks with and without the make constraints