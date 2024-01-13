---
layout: page
title:
permalink: /writing-papers/
nav: false
nav_order: 5
---

# Writing Academic Papers 

This page discusses my preferences when it comes to writing papers. It is more focused on paper structuring and collaboration, as opposed to lower-level writing tips. It is not meant to be a golden standard in any way, and I do not claim that my preferences are the *right* way to do anything. This is primarily meant for my students -- specifically, to avoid having to repeat myself every time I start working with a new student (inspired by [Claire Le Goues'](https://clairelegoues.com/2016/08/23/things-i-keep-repeating-about-writing/) post a while back). However, if you find this information useful, or want to use a similar setup, please go ahead! I will update this as I think of more points (or maybe find strong reasons to do things in another way down the road).

## Setup & Directory Structure

* For every new paper we work on, please create a private GitHub repository under our GitHub organization with the following name `paper-<your last name>-<name of the conference we plan to submit to>`. For example, if I was the main author of the paper and planning to submit the work to ICSE '18, I would name it `paper-nadi-icse18`. Suppose we started working on a paper, but still don't have a concrete venue in mind. In that case, use some descriptive phrase. For example, if we were working on extracting configuration constraints, the repo name would be `paper-nadi-config-constr`. *Credits:* I learned this naming strategy during my time at TU Darmstadt and found it quite useful, since typically a group's GitHub organization would have a mix of paper repos, code repos, grant repos etc. Having some fixed prefix for papers made them easier to spot.

* We will write all papers using [LaTeX](https://www.latex-project.org/). If you don't know LaTeX, now is the time to learn.

* If we are targetting a specific conference, make sure to get the right template for the conference. It would be such a pity to get a desk reject, because of using the wrong template! If we are not sure which conference we will target, then just use the standard [ACM](http://www.acm.org/publications/proceedings-template) or [IEEE](https://www.ieee.org/conferences_events/conferences/publishing/templates.html) template for the time being, but make sure to switch to the right one when we decide on a conference

* Rename the main LaTeX file as `main.tex` and keep it in the main directory. Create a separate `tex` file for each section in the paper, and organize the directory as follows (this example assumes we are using the ACM template):

```
main.tex
ACM-Reference-Format.bst
acmart.cls
sections/
	introduction.tex
	related-work.tex
	...
meta/
	packages.tex
	macros.tex
	any-other-definition-files.tex
images/
	linux-evolution.pdf
	any-other-figure-in-the-paper.pdf
references/
	references.bib
	any-other-ref-files-as-needed.bib
```

The idea is to include the other files in the `main.tex` file as needed. This is would be an example of what `main.tex` looks like:


```
\documentclass[sigconf,review,anonymous]{acmart}

\input{meta/packages}
\input{meta/macros}

%Conference
\acmConference[ICSE'18]{International Conference on Software Engineering}{May 2018}{Gothenburg, Sweden} 
\acmYear{2018}
\copyrightyear{2018}

\acmPrice{15.00}


\begin{document}
  
\title{Our Awesome Paper}

% all the author information

\input{sections/abstract}


\maketitle

\input{sections/introduction}
\input{sections/motivation}
...
\input{sections/related-work.tex}
\input{sections/conclusion}

\newpage

\balance

\bibliographystyle{ACM-Reference-Format}
\bibliography{references/references}

\end{document}
```

* Please do not include any generated files in the git repository (e.g., .blg, .log, .aux etc.). This also includes the `main.pdf` file.

## Collaboration

* We will collaborate through the git repository. So **please please please** commit regularly and push the repo. You don't have to wait till you have finished the whole section and revised it 5 times before pushing it to the repo. I will not read it anyways until you tell me it is ready so commit often so we have good history in case something goes wrong and so we don't loose all your writing in case your computer crashes.

* For early drafts, I would typically mark up a pdf and send it to you or we would sit together and go through a printed section where I'll mark up things as we go. In either case, I expect that you will update things in the repository afterwards. In later stages, once the content is a bit stable, I will typically start editing things in the repository. This will usually be through leaving comments in the text. To make it easier for me to leave comments and for you to respond to them if necessary, always have the following macros defined (obviously, change colors as needed). If a comment has already been addressed and resolved, then remove it from the text.

{% raw %}
```
\newcommand{\sn}[1]{{\color{blue} \textbf{Sarah:}~#1}}
\newcommand{\<your initials>}[1]{{\color{green}\textbf{<Your Name>:}~#1}}
```
{% endraw %}

* There may be some parts of the paper still under construction, e.g., numbers you still need to get or a citation you still need to find. For these, have a TODO macro defined such that we can easily spot what's left to do:

{% raw %}
```
\newcommand{\todo}[1]{{\textcolor{red}{\textbf{TODO:}~#1}}
```
{% endraw %}

* To make sure we can clearly see numbers that need to be double checked, surround all numbers with the following `\checkNum` macro. Make sure to remove the coloring from the macro before submitting. *Credits*: again, this is another trick I learned from TU Darmstadt students.

{% raw %}
```
\newcommand{\checkNum}[1]{{\textcolor{orange}{\textit{#1}}}
```
{% endraw %}

* When you are the only one working on the repository, there are no chances of conflicts. However, if we are both editing the paper, we should coordinate such that we are not both editing the same sections (that's why I like each section to go in a separate file). We can do this via Slack or email.


* Before you try pulling changes into your local repository, make sure to commit your current changes first and then do `git pull --rebase`. Do the same before pushing changes. This decreases the chances of us getting unnecessary merge conflict messages and provides a cleaner history for us (i.e., no unnecessary merges).

* While I have not strictly implemented this myself so far, I think it is a good idea to have each sentence in a separate line (Sebastian Proksch at TU Darmstadt, now at U. Zürich used to follow this). This makes it easier to diff versions and resolve conflicts. I will try to implement this myself going forward.


## Writing Style

* I don't claim to be the world's best writer, but I have several pet peeves:
	* make sure you know when to use `the` vs. `a` vs. neither. If you find me constantly adding or removing `the`'s from your text and you don't understand what the problem is, come ask me why. Please do not just keep doing the same thing over and over again; it's frustrating for both of us.	
	* If you have a sentence that's four lines long, it is likely confusing and hard to understand. Break it down. The more concisely you can say something the better. If you need more words, use multiple sentences. You need to take the reader through the flow of your arguments. Don't loose readers by forcing them to go back and read each sentence or paragraph twice. Make their life easier. Reviewers are already picky as it is.. don't give them another reason to shoot your paper down.
	* To avoid typing a long list (and it's hard to remember all of them now), Claire Le Goues' [post](https://clairelegoues.com/2016/08/23/things-i-keep-repeating-about-writing/) has good tips on writing style. However, note how she prefers having the whole paper in one file and I don't ? -- hence, each advisor's personal preferences.

* In general, be prepared to do multiple iterations on the paper. We might end up re-organzing things several times. Be patient and give yourself enough time ahead of the deadline for these iterations.
	
## Paper Organization 

* I always remember my PhD advisor, [Ric Holt](https://plg.uwaterloo.ca/~holt/), for the words "big picture". They are now engraved in my brain. So what do they mean? You always want to tell the reader what the big picture is. What's the context of the problem you are dealing with? What exactly are you doing? Why should they care about what you are doing? Who will benefit out of the results? How can the results be used? A good paper never leaves the reader wondering about any of these points. Ideally, the introduction should already answer a lot of these "big picture" questions without necessary overwhelming the reader with tons of low-level details or side "stories". 

* Related to big pictures, I'm a big fan of overview figures that provide a numbered or labelled illustration of all steps of the methodology or the components of a framework, for example. These numbers can then be referenced in the text, and make life so much easier for the reader. They also force you to write in a more structured way. Examples: [Figure 1](https://dl.dropboxusercontent.com/s/j4gu0145t4ry0xs/Proksch_ASE16.pdf), [Figure 1](https://dl.dropboxusercontent.com/s/4pus24phiq7gmmt/Proksch_SANER17.pdf), or [Figure 1](https://dl.dropboxusercontent.com/s/f9gy8kzv6dwwwgl/NADI_ICSE14.pdf). Notice how they are all Figure 1 :-)

## Updating Results

* Ideally, you want to create your experiments such that it is easy to re-run them and update the results in the paper as needed.

* For figures, plots etc., the best way to do this is to have a script for reproducing the graph. So we can basically update a label, re-run the script and then re-compile our LaTeX file. If you already do your figures in LaTeX (I personally don't just because I never tried it not because I have anything against it), then you already guarantee they are always up to date.

* Ideally, also have a script that does everything. This script can call multiple other scripts/programs, but it should go through the whole pipeline of data analysis etc. until reproducing plots and tables. Basically, re-run your experiment from A-Z with a click of a button. Depending on the situation, this may not always be feasible but it's great to have.

* One way to make the recreation of tables easier is to have each table in a separate .tex file and have a script that generates it.

* For numbers in the text, you can create scripts that output a .tex file with some of the results you will use in the paper. I will use my ICSE '16 paper as an example. On the [artifact page](http://www.st.informatik.tu-darmstadt.de/artifacts/crypto-api-misuse/), you will find the [R script](http://www.st.informatik.tu-darmstadt.de/artifacts/crypto-api-misuse/Data/Study4/survey_analysis.r) I used for all my data analysis. This R script also outputted certain values to a `survey_data.tex` file, which looked like this:

```
\pgfkeyssetvalue{total_responded}{43}
\pgfkeyssetvalue{ignored}{6}
\pgfkeyssetvalue{total_analyzed}{37}
\pgfkeyssetvalue{percentage_students}{11}
\pgfkeyssetvalue{percentage_professional}{54}
\pgfkeyssetvalue{percentage_six_years}{73}
\pgfkeyssetvalue{percentage_atleast_knowledgeable}{86}
\pgfkeyssetvalue{percentage_rarely_need_crypto}{57}
\pgfkeyssetvalue{percentage_secure_comm_rank1}{49}
\pgfkeyssetvalue{percentage_user_auth_rank1}{30}
\pgfkeyssetvalue{user_auth_avg_rank}{3.95}
...
```

This data file was included in `main.tex` as follows:

```
\input{results/survey_data.tex}
```

To use any of these values in the text of a particular section in the paper, you would do:

```
We base our findings below on the remaining \checkNum{\pgfkeysvalueof{total_analyzed}} participants. 
```

You do need to have `\usepackage{pgfkeys}` to be able to use this (*Credits:* I learned about this package from the Undertaker group at Erlangen). Obviously, there may be other ways to do something similar. The point is that you could re-run an external script that would regenerate all numbers and you don't have to go and manually update each number in your tex files.
