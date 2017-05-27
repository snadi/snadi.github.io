---
layout: post
title: Code Recommender Systems
date: 2016-10-26 16:37:00
permalink: /config-constraints/
group: research
tags: completed
weight: 1
---

One of the ways to avoid API misuse is to create code recommender systems that help developers write better code in the first place. A challenge here is to gather real-world data about how developers use these APIs and the available code recommender tools. We looked at code recommenders from different angles. 

* In our [SWAN '16] paper, we looked at scalability of Java method-call recommenders that simply tell the developer which method to call next. 
* Evaluation is one of the challenges faced while building code recommender systems. In our [SANER '16] paper, we developed an open-source interaction tracker tool for the Visual Studio Integrated Development Environment (IDE) that monitored how developers use the IDE, particularly how they use the IDE’s built-in code completion tool [1]. This work was the first study that captured interactions in Visual Studio from a variety of users, including industrial developers. Using the data collected, we created, for the first time, a publicly available fine-grained record of how exactly code evolves over time [21]. We used this record as a ground truth to evaluate how researchers typically evaluate their code recommender engines. Our results show that certain code evolution aspects, such as changing the way an object is defined, have a negative effect on the prediction quality of recommender systems [2, 13]. However, since released code includes only a snapshot of the final state of the code, these evolution aspects are no longer identifiable. This means that offline evaluations that rely on released code typically see an inflated prediction quality of the evaluated recommenders. Our work was the first to empirically evaluate the assumptions that researchers make when designing the evaluations of our tools. Furthermore, the data sets and tools we created in this line of work [12,
Sarah Nadi 4 13] are important contributions to the field, enabling the systematic comparison of recommender
systems that help developers use APIs.

###Involed Researchers
* Sven Amann
* Ervina Cergani
* Sebastian Proksch