---
layout: post
title: API Misuse Detection
date: 2016-10-26 16:22:00
permalink: /smr/api-misuse/
group: research
tags: current
weight: 3
short-desc: When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as misuses. One example of a misuse is forgetting to call close() after opening a FileInputStream and writing to it. There are various categories of API-misuses, and most of the current misuse detectors only find some of these categories. 
long-desc: When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as misuses. One example of a misuse is forgetting to call close() after opening a FileInputStream and writing to it. There are various categories of API-misuses, and most of the current misuse detectors only find some of these categories. Our goal is to systematically design a misuse-detector that can cover most of these categories. As a first step, we created MUBench, a benchmark of existing API-misuses against which we can evaluate several misuse-detectors. We then systematically compared existing Java API-misuse detectors and identified weaknesses. This allowed us to design a new API misuse detector, MuDetect, that can achieve higher recall and precision. 
key: api-misuse
pubs: AmannTSE18,AmannMSR16,AmannMSR19
img: /resources/images/mubench.png
related-urls:
   - title: MUBench
     url: https://github.com/stg-tud/MUBench
   - title: MUDetect
     url: https://github.com/stg-tud/mudetect
---

{% include project-details.html page=page %}
