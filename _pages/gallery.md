---
title: "Gallery"
permalink: /gallery/
layout: single
author_profile: true
---

A collection of photos from my adventures.

<div class="gallery-tabs">
  {% for gallery in site.data.galleries %}
    <button class="tab-link" onclick="openGallery(event, '{{ gallery.id }}')">{{ gallery.category }}</button>
  {% endfor %}
</div>

{% for gallery in site.data.galleries %}
<div id="{{ gallery.id }}" class="tab-content">
  <div class="gallery-grid">
    {% for image in gallery.images %}
      <div class="gallery-item">
        <a href="{{ image.url | relative_url }}" title="{{ image.alt }}">
          <img src="{{ image.url | relative_url }}" alt="{{ image.alt }}" />
        </a>
      </div>
    {% endfor %}
  </div>
</div>
{% endfor %}

<script>
  function openGallery(evt, galleryName) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tab-content");
    for (i = 0; i < tabcontent.length; i++) {
      tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tab-link");
    for (i = 0; i < tablinks.length; i++) {
      tablinks[i].className = tablinks[i].className.replace(" active", "");
    }
    document.getElementById(galleryName).style.display = "block";
    evt.currentTarget.className += " active";
  }
  // Get the first tab and click it to open by default
  document.getElementsByClassName("tab-link")[0].click();
</script>