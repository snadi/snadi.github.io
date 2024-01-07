---
layout: project
title: Software Variability
description: Creating & maintaining variants of the same system
importance: 4
category: completed
img:  assets/img/projects/var-anomalies.png
related_publications: NadiJSEP2013,NadiDS2013,NadiMSR2013,NadiCSMR2012,NadiWCRE2011, Medeiros2015, NadiTSE2015, NadiICSE2014, ALMasriSPLC18,AlMasriCASCON17, NuryyevICSE21, BusingeICSEM18,BusingEMSE22
related-urls:
    - title: Farce Appendix (for Reverse Engineering Configuration Constraints)
      url: http://gsd.uwaterloo.ca/farce
    - title: Farce Source Code
      url: https://bitbucket.org/snadi/farce
    - title: OMR Statistics
      url: https://github.com/samasri/omr/tree/master/tools/compiler/OMRStatistics
    - title: VarClang
      url: https://github.com/ualberta-smr/varclang
    - title: BruteClang
      url: https://github.com/nbhuiyan/BruteClang
    - title: Makex (CSMR 2012 paper)
      url: https://github.com/snadi/makex 
    - title: Linux Variability Anomalies Evolution (MSR 2012 paper)
      url: https://github.com/snadi/LinuxVarAnomalyEvolution 
---

Software reuse is essential to build software faster. Different customers or platforms may need different features of the same software system. Instead of copy-and-paste mechanisms where different copies of the system is maintained, using Software Product Lines (SPLs) or Highly Configurable Software is a way to systematically create and maintain different variants of the same system.

We have a long line of work in this area, exploring different aspects of creating and maintaining SPLs. A lot of this work is done on the Linux kernel, as an exemplar of an extremely large and popular highly configurable system. We also explored other systems such as [Eclipse OMR](https://github.com/eclipse/omr) and Android App software families.
