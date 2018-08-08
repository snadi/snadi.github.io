---
layout: page
title:
permalink: /smr/members/
---

# Members of the Software Maintenance and Reuse Lab 

![Software Maintenance and Reuse Lab]({{ "/resources/images/logo_web_color_2400_frame_transparent.png" }}){:height="200px" width="200px" align="right"}

<div>
<h1>Faculty Members</h1>
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


<div class="row" >
<h2>Current PhD Students</h2>
<br/>
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


<div class="row" >
<h2>Current Master's Students</h2>
<br/>
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
<h2> Current Undergraduate Students</h2>
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


<div class="row" >
<h2>SMR Alumni </h2>
{% assign alumini = (site.staff | where: 'status','previous' | sort:'end-year', 'last') | reverse %}

{% for member in alumini %}


<div class="medium-3 columns" >


<p>
<figure>
<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >

<figcaption>
<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
<br/>
{{ member.position }}, {{ member.start-year }} - {{ member.end-year }}
</figcaption>
</figure>
</p>

</div>

{% endfor %}
</div>



</div>
