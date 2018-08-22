---
layout: page
title:
permalink: /smr/photo-gallery
images:
  - image_path: /resources/gallery/lunches/group-lunch-jul2018.JPG
    title: Group Lunch, July 2018
  - image_path: /resources/gallery/lunches/group-lunch-oct2017.jpeg
    title: Group Lunch, October 2017
  - image_path: /resources/gallery/posters/poster-cascon17-nazim.JPG
    title: CASCON '17 poster presentations in Markham, ON (Nazim Bhuiyan)
  - image_path: /resources/gallery/posters/poster-cascon17-samer.JPG
    title: CASCON '17 poster presentations in Markham, ON (Samer Al Masri)
  - image_path: /resources/gallery/presentations/presentaiton-cascon17-samer.JPG
    title: Samer's CASCON '17 presentation in Markham, ON
  - image_path: /resources/gallery/presentations/presentations-icse18-fernando.JPG
    title: Fernando's ICSE '18 NIER presentation in Gothenburg, Sweden
  - image_path: /resources/gallery/presentations/presentations-msr18-mehran.JPG
    title: Mehran's MSR '18 presentation in Gothenburg, Sweden

---

<style>
    
    .image-gallery img {width:500px;}
</style>

{% for image in page.images %}
<div class="image-gallery">
  
    <figure>
    <a href= "{{ image.image_path }}">
        <img src="{{ image.image_path }}" alt="{{ image.title}}"/>
    </a>
    <figcaption>
        {{ image.title }}
    </figcaption>
    </figure>

</div>
  {% endfor %}