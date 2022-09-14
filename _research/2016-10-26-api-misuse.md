---
layout: post
title: API Misuse Detection
date: 2016-10-26 16:22:00
permalink: /smr/api-misuse/
group: research
tags: current
weight: 3
short-desc: When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as misuses. One example of a misuse is forgetting to call close() after opening a FileInputStream and writing to it. There are various categories of API-misuses, and most of the current misuse detectors only find some of these categories. 
long-desc: When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as misuses. One example of a misuse is forgetting to call close() after opening a FileInputStream and writing to it. There are various categories of API-misuses, and most of the current misuse detectors only find some of these categories. Our goal is to systematically design a misuse-detector that can cover most of these categories. As a first step, we created MUBench, a benchmark of existing API-misuses against which we can evaluate several misuse-detectors. We then systematically compared existing Java API-misuse detectors and identified weaknesses. This allowed us to design a new API misuse detector, MuDetect, that can achieve higher recall and precision. <p>MuDetect allows us to mine API usage rules that involve method calls and preconditions. These usage rules are then used to find misuses in target projects. MuDetect uses a graph representation called an API Usage Graph (AUG) to represent different aspects of a method call such as the parameters that are required by a method, the types of those parameters, the order in which different method calls are invoked, the exceptions thrown by different method calls, objects that are returned by different method calls.</p><p>While MuDetect focuses on method calls, there are other categories of APIs misuses as well, such as misuses that involve annotations. We have built a tool that focuses on producing accurate annotation usage rules with the help of human experts. For the ease of usability, these usage rules are packaged into a Maven plugin that can be used to catch bugs (similar to SpotBugs). Our tool is a complete pipeline that provides an easy way to mine and validate usage rules, and generate a misuse detector from confirmed rules.</p>
key: api-misuse
pubs: AmannMSR19,AmannTSE18,AmannMSR16
img: /resources/images/mubench.png
related-urls:
   - title: MUBench
     url: https://github.com/stg-tud/MUBench
   - title: MUDetect
     url: https://github.com/stg-tud/mudetect
   - title: Annotation Usage Rule Generation Pipeline
     url: https://github.com/ualberta-smr/generating-annotation-usage-rules
---

{% include project-details.html page=page %}
