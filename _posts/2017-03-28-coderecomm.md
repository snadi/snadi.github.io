---
layout: post
title: Code Recommender Systems
date: 2016-10-26 16:37:00
permalink: /config-constraints/
group: research
tags: completed
weight: 1
---

One of the ways to avoid API misuse is to create code recommender systems that help developers write better code in the first place. A challenge here is to gather real-world data about how developers use these APIs and the available code recommender tools. We looked at code recommenders from different angles. <!--more-->

* In our [SWAN '16] paper, we looked at scalability of Java method-call recommenders that simply tell the developer which method to call next. 

* Evaluation is one of the challenges faced while building code recommender systems. In our [SANER '16](/resources/pubs/Amann_SANER16.pdf) paper, we developed an open-source interaction tracker tool for the Visual Studio Integrated Development Environment (IDE) that monitored how developers use the IDE, particularly how they use the IDE’s built-in code completion tool. This work was the first study that captured interactions in Visual Studio from a variety of users, including industrial developers. Using the data collected, we created, for the first time, apublicly available fine-grained record of how exactly code evolves over time. In our [ASE '16](/resources/pubs/Proksch_ASE16.pdf) paper, we used this record as a ground truth to evaluate how researchers typically evaluate their code recommender engines. Our results show that certain code evolution aspects, such as changing the way an object is defined, have a negative effect on the prediction quality of recommender systems. However, since released code includes only a snapshot of the final state of the code, these evolution aspects are no longer identifiable. This means that offline evaluations that rely on released code typically see an inflated prediction quality of the evaluated recommenders. Our work was the first to empirically evaluate the assumptions that researchers make when designing the evaluations of our tools. 

* The tools in this line of work are part of the [KaVe](http://kave.cc) project, lead by Sebastian Proksch. 

* You can find details about the Visual Studio interaction tool in our [ICPC '16](/resources/pubs/Amann_ICPC16.pdf) tool paper. You can also find a publicly available dataset of source code information of open-source C# projects in our [MSR '16](/resources/pubs/Proksch_MSR16.pdf) data paper.

###Involed Researchers
* Sven Amann
* Ervina Cergani
* Sebastian Proksch