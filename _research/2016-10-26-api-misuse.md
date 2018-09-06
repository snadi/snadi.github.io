---
layout: post
title: API Misuse Detection
date: 2016-10-26 16:22:00
permalink: /smr/api-misuse/
group: research
tags: current
weight: 3
---

When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as misuses. One example of a misuse is forgetting to call close() after opening a FileInputStream and writing to it. There are various categories of API-misuses, and most of the current misuse detectors only find some of these categories. <!--more-->Our goal is to systematically design a misuse-detector that can cover most of these categories. As a first step, we created MUBench, a benchmark of existing API-misuses against which we can evaluate several misuse-detectors. To find more about our collected data set and our automated pipeline for running detectors and reviewing their results, please checkout our [MUBench page](https://github.com/stg-tud/MUBench). 