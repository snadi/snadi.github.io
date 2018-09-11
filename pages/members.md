---
layout: page
title: SMR Members
permalink: /smr/members/
---

# Members of the Software Maintenance and Reuse Lab


<h3>Faculty Members</h3>

<div class="row">
	{% for member in site.staff %}
		{% if member.role == "Faculty" %}

		<div class="medium-3 columns">

			<figure>
				<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

				<figcaption>
					<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
				</figcaption>
			</figure>
		</div>

		{% endif %}    
	{% endfor %}
</div>

<br/>


<h3>Current PhD Students</h3>

<div class="row">
	{% for member in site.staff %}

		{% if member.position=="PhD" and member.status=="current"%}

			<div class="medium-3 columns"  >

				<figure>
				<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

				<figcaption>
				<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
				</figcaption>
				</figure>
			</div>
		{% endif %}    

	{% endfor %}
</div>



<h3>Current Master's Students</h3>

<div class="row" >
	{% for member in site.staff %}

		{% if member.position=="MSc." and member.status=="current" %}

			<div class="medium-3 columns"  >

				<figure>
				<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

				<figcaption>
				<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
				</figcaption>
				</figure>
			</div>
		{% endif %}    

	{% endfor %}
</div>

<div class="row" >
<h3> Current Undergraduate Students</h3>
<br/>
{% for member in site.staff %}

{% if member.position=="Undergrad RA" and member.status=="current" %}

<div class="medium-3 columns" >

<figure>
<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

<figcaption>
<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
</figcaption>
</figure>

</div>
{% endif %}    

{% endfor %}
</div>


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
