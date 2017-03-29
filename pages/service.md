---
layout: page
title:
permalink: /service/
---

# Current #
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
<div>nowunix {{ nowunix}} </div>
{% for service in site.service %}
<div>boo</div>
	{% capture endservice %}{{service.end_date | date: '%s'}}{% endcapture %}
	<div>endservice {{ endservice }} </div>
	{% if endservice >= nowunix %}
		{% if service.role == "pc" %}

			* **Program Committee Member**, [{{service.title}}]({{service.link}})
		{% endif %}
	{% endif %}
{% endfor %}

<!-- * **Program Committee Member**, [OOPSLA '17](http://2017.splashcon.org/track/splash-2017-OOPSLA)
* **Program Committee Member**, [MSR '17](http://2017.msrconf.org/#/home)
* **Program Committee Member**, [GPCE '17](http://conf.researchr.org/track/gpce-2017/gpce-2017-GPCE-2017)
* **Program Committee Member**, [SPLC '17](http://congreso.us.es/splc2017/)
* **Program Committee Member**, [VaMoS '17](https://vamos2017.wordpress.com/)
* **Program Committee Member**, [SANER '17 -- Early Research Achievements Track](http://saner.aau.at/call-for-papers-era-track/)
* **Co-Chair**, [SANER '17 -- Poster Track](http://saner.aau.at/call-for-papers-poster-track/)
* **Program Committee Member**, [ICPC '17 -- Tools Demo Track](http://icpc2017.unibas.it/)


 -->
# Past #


