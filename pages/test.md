---
layout: page
title: Test
permalink: /test/
---
<div>
<h1>Faculty Members</h1>
<div class="row">
  {% for member in site.staff %}
   {% if member.role == "Faculty" %}

 <div class="medium-3 columns">
 
    <img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}" class="members" alt="{{ member.name }}">
    <p>
        <a href="{{member.website }}" target="_blank">
          {{ member.name }} 
        </a>
      </p>
	</div>

  {% endif %}	
   {% endfor %}
   	</div>
	<br/>

 
<!--    <div class="row" >-->
<!--    <h2>Postdocs</h2>-->
<!--    <br/>-->
<!--   {% for member in site.staff %}-->
<!--    -->
<!--      {% if member.title=="Postdocs"%}-->
<!--      -->
<!--     <div class="medium-3 columns" >-->
<!--     -->
<!--    <img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}" class="members" >-->
<!--    <p>-->
<!--        <a href="{{member.website }}" target="_blank">-->
<!--          {{ member.name }} -->
<!--        </a>-->
<!--      </p>-->
<!--    -->
<!--        </div>-->
<!--{% endif %}    -->
<!--     -->
<!--  {% endfor %}-->
<!--         </div>-->

	
	<div class="row" >
	<h2>Current PhD Students</h2>
		<br/>
   {% for member in site.staff %}
	
	  {% if member.title=="phd"%}
	  
	 <div class="medium-3 columns"  >
	 
    <img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}" class="members"  >
    <p>
	{% if member.website == "" %}
	{{member.name}}
	{% else %}
        <a href="{{member.website }}" target="_blank">
          {{ member.name }} 
        </a>
		{% endif %}
      </p>
	
		</div>
{% endif %}	
 	
  {% endfor %}
     	</div>

	
	<div class="row" >
	  <h2>Current Master's Students</h2>
	  	<br/>
	 {% for member in site.staff %}
	
	  {% if member.title=="master" and member.status=="current" %}
	
	 <div class="medium-3 columns"  >
	 
    <img  src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}" class="members"  >
    <p>
      {% if member.website == "" %}
	{{member.name}}
	{% else %}
        <a href="{{member.website }}" target="_blank">
          {{ member.name }} 
        </a>
		{% endif %}
      </p>
	
		</div>
{% endif %}	
 	
  {% endfor %}
     	</div>
		
	<div class="row" >
	  <h2> Current Undergraduate Students</h2>
	  	<br/>
	 {% for member in site.staff %}
	
	  {% if member.title=="undergrad"%}
	
	 <div class="medium-3 columns" >
	 
    <img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >
    <p>
       {% if member.website == "" %}
	{{member.name}}
	{% else %}
        <a href="{{ member.website }}" target="_blank">
          {{ member.name }}
        </a>
		{% endif %}
      </p>
	
		</div>
{% endif %}	
 	
  {% endfor %}
     	</div>
		
		
		<div class="row" >
	  <h2>SMR Alumni </h2>
	 {% for member in site.staff %}
	
	  {% if member.status=="previous"%}
	
	 <div class="medium-3 columns" >
	 
    
    <p>
    	<figure>
    		<img src="{{ site.baseurl }}/staff/image/{{ member.profile_photo_path_staff }}"  class="members"  >
        
	        <figcaption>
	        	<a href="{{member.website }}" target="_blank">{{ member.name }}</a>
	        	<br/>
	        	{{ member.degree }}, {{ member.year }}
	        </figcaption>
        </figure>
      </p>
	
		</div>
{% endif %}	
 	
  {% endfor %}
     	</div>
		
		
		
    </div>
