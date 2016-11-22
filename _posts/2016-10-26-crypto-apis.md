---
layout: post
title: Cryptography APIs
date: 2016-10-26 16:37:00
permalink: /crypto-apis/
excerpt_separator: <!--more-->
group: research
tags: current
weight: 4
---

Previous research has shown that many security vulnerabilities exist due to developer's misuse of cryptography APIs. In other words, developers make mistakes while using the APIs and these mistakes can lead to serious security threats. In this project, we wanted to investigate the reasons for such mistakes and suggest reasons on how to improve the situation. <!--more-->Through analyzing StackOverflow posts, GitHub repositories, and conducting two surveys of a total of 48 application developers, we collect the problems developers face with the current cryptography APIs and their suggestions for improvement. To find out more about this study, please check out our [ICSE '16](https://dl.dropboxusercontent.com/s/1bantpje27z4p0s/NADI_ICSE16.pdf) paper and our artifact page.

Some of our findings included that developers have problems choosing the correct algorithm to use and also want higher level abstractions such as tasks. To address these issues, we looked closer at the cryptography domain, and realized that there is a wide variety of cryptographic components and algorithms (e.g., ciphers, digests, signatures, etc.) and that each of these components comes with its own *variability*. For example, a cipher can be symmetric or asymmetric. If it is symmetric, it can operate on blocks or streams. Additionally, there are different modes of operations (e.g., ECB vs CBC) as well as different padding schemes. In order to deal with this huge variability space, we model cryptographic components using concepts from feature modeling. However, such components have many attributes. Additionally, some cryptography solutions may use multiple components at the same time. We, therefore, need additional modeling notations than those offered by basic feature modeling.

We are currently using Clafer as a modeling language and investigating its ability to successfully model cryptography components. You can read more about our experience using Clafer in our [VaMoS '16](https://dl.dropboxusercontent.com/s/47jsvcjxsvdq80x/NADI_Vamos16.pdf) paper. The variability model we are developing will be used as a part of a software product line solution for automatically generating code snippets corresponding to common cryptography tasks. Thus, application developers can select the tasks they need (e.g., store password) and configure components according to their needs before getting the corresponding code snippet. More details about how our proposed solution works can be found in our [ONWARD! '15](https://dl.dropboxusercontent.com/s/5rfyf3a9bqheyv9/Arzt_Onward2015.pdf) paper.

