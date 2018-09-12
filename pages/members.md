---
layout: page
title: SMR Members
permalink: /smr/members/
---

# Members of the Software Maintenance and Reuse Lab


<h3>Faculty Members</h3>

{% include filteredmembers-status.html position="Faculty" status="current" %}

<br/>


<h3>Current PhD Students</h3>

{% include filteredmembers-status.html position="PhD" status="current" %} 

<br/>

<h3>Current Master's Students</h3>

{% include filteredmembers-status.html position="MSc." status="current" %} 

<br/>

<h3> Current Undergraduate Students</h3>

{% include filteredmembers-status.html position="Undergrad RA" status="current" %} 

<br/>


<h3>SMR Alumni </h3>
{% assign alumini = (site.staff | where: 'status','previous' | sort:'end-year', 'last') | reverse %}


<div class="row" >
	{% for member in alumini %}


		<div class="medium-3 columns" >

			<figure>
				<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

				<figcaption>
				<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
				<br/>
				{{ member.position }}, {{ member.start-year }} - {{ member.end-year }}
				</figcaption>
			</figure>

		</div>

	{% endfor %}
</div>
