---
layout: project
title: API Misuse
description: Ensuring that library APIs are correctly used
img: assets/img/projects/mubench.png
importance: 1
category: active
related_publications: GulamiCASCON22,NuryyevICSME22,AmannMSR19,AmannTSE18,AmannMSR16,KruegerASE17,NadiICSE2016,NADIVamos16,ArztOnward2015,KrugerSecDev23,GalaESEM2024
related-urls:
   - title: MUBench Repository
     url: https://github.com/stg-tud/MUBench
   - title: MUDetect Repository
     url: https://github.com/stg-tud/mudetect
   - title: Annotation Usage Rule Generation Pipeline Repository
     url: https://github.com/ualberta-smr/generating-annotation-usage-rules
   - title: CogniCrypt Project
     url: https://projects.eclipse.org/proposals/eclipse-cognicrypt     
---


When developers use Application Programming Interfaces (APIs), they often make mistakes that can lead to bugs, system crashes, or security vulnerabilities. We refer to such mistakes as <i>misuses</i>. One example of a misuse is forgetting to call <code>close()</code> after opening a <code>FileInputStream</code> and writing to it. 

We study various types of API misuse.

### API Misuse of Data-centric Python Libraries

<div class="justify-content-sm-center">
<div class="col-sm-4 mt-3 mt-md-0 justify-content-sm-center">
        {% include figure.html path="assets/img/projects/data-centric-misuse.png" title="Example of a data-centric misuse" class="img-fluid rounded z-depth-1" %}
</div>
Data-centric Python libraries, such as pandas, matplotlib etc., often deal with diverse data structures, intricate processing workflows, and a multitude of parameters, which can make them inherently more challenging to use correctly. Detecting problems in the usage of these libraries is challenging, not only due to the dynamic nature of Python but due to the fact that some misuses depend on the data that is being processed. In this line of work, we investigate how API misuse manifests in these data-centric libraries and how we can design successful detection strategies to help developers use them correctly.
</div>



### General Java API Misuse

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/mubench.png" title="MuBench" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/mudetect.png" title="MuDetect" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

We created MUBench, a benchmark of existing Java API misuses against which we can evaluate several misuse-detectors. We systematically compared existing Java API-misuse detectors and identified weaknesses. This allowed us to design a new API misuse detector, [MuDetect](https://github.com/stg-tud/mudetect), that can achieve higher recall and precision. MuDetect allows us to mine API usage rules that involve method calls and preconditions. These usage rules are then used to find misuses in target projects. MuDetect uses a graph representation called an API Usage Graph (AUG) to represent different aspects of a method call such as the parameters that are required by a method, the types of those parameters, the order in which different method calls are invoked, the exceptions thrown by different method calls, objects that are returned by different method calls.

### Annotation Misuse in Java

<div class="justify-content-sm-center">
<div class="col-sm-4 mt-3 mt-md-0 justify-content-sm-center">
        {% include figure.html path="assets/img/projects/rvt.png" title="Rule Validation Tool" class="img-fluid rounded z-depth-1" %}
</div>
</div>

While MuDetect focuses on method calls, there are other categories of APIs misuses as well, such as misuses that involve annotations. We built a [human-in-the-loop approach](https://github.com/ualberta-smr/generating-annotation-usage-rules) that focuses on producing accurate Java annotation usage rules. For the ease of usability, these usage rules are packaged into a Maven plugin that can be used to catch bugs (similar to SpotBugs). Our tool is a complete pipeline that provides an easy way to mine and validate usage rules, and generate a misuse detector from confirmed rules.

### Java Cryptography Misuse

Through analyzing StackOverflow posts, GitHub repositories, and conducting two surveys of a total of 48 application developers, we collect the problems developers face with the current cryptography APIs and their suggestions for improvement. Some of our findings included that developers have problems choosing the correct algorithm to use and also want higher level abstractions such as tasks. To address these issues, we looked closer at the cryptography domain, and realized that there is a wide variety of cryptographic components and algorithms (e.g., ciphers, digests, signatures, etc.) and that each of these components comes with its own *variability*. For example, a cipher can be symmetric or asymmetric. If it is symmetric, it can operate on blocks or streams. Additionally, there are different modes of operations (e.g., ECB vs CBC) as well as different padding schemes. In order to deal with this huge variability space, we model cryptographic components using concepts from feature modeling. However, such components have many attributes. Additionally, some cryptography solutions may use multiple components at the same time. We, therefore, need additional modeling notations than those offered by basic feature modeling. 

[CogniCrypt](https://projects.eclipse.org/proposals/eclipse-cognicrypt) was built on the insights derived from these studies.



