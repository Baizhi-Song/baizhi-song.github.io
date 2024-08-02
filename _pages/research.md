---
layout: archive
title: "Research"
permalink: /research/
header:
#   teaser: /LBS-Logo.png
    overlay_image: /01_TOC/TOC_system03.jpg
#   image: /LBS-Logo.png
#   header: /LBS-Logo.png
    # overlay_color: "#333333" 
    # overlay_filter: 0.1
author_profile: true

---

## Ocean Cleaning 

<!-- <a href="{{ site.baseurl }}/research/ocean_cleanup.html" style="display: inline-block; padding: 4px 8px; font-size: 16px; color: white; background-color: #52acc8; text-align: center; text-decoration: none; border-radius: 5px;">Website</a> -->

Increasing ocean plastic pollution is irreversibly harming ecosystems and human economic activities. We partner with a Dutch NGO, <a href="https://theoceancleanup.com/">The Ocean Cleanup (TOC)</a>, and use optimization to help clean up oceans from plastic faster. 
In our paper, we optimize the route of their plastic collection system in the ocean to maximize the quantity of plastic collected over time.
On one-year ocean data, our optimization-based routing approach increases the quantity of plastic collected by over 60% compared with their current routing strategy, hence speeding up the progress towards plastic-free oceans.
<div style="display: flex; align-items: flex-start; margin-bottom: 10px;">
  <figure style="max-width: 40%; margin: 23px;">
    <div style="clip-path: inset(0% 0% 0% 0%);">
        <img src="/images/01_TOC/TOC_system02.jpg" alt="Animation of cleaning route" style="width: 100%; height: auto;">
    </div>
    <figcaption style="text-align: center; padding: 5px 0;">Cleaning system 002 built by TOC. Credit: <a href="https://theoceancleanup.com/media-gallery/">The Ocean Cleanup</a></figcaption>
  </figure>
  <figure style="max-width: 55%; margin: 0;">
    <div style="clip-path: inset(0% 0% 0% 0%);">
        <img src="/images/01_TOC/path_demo_weather_2month_HD-ppt.gif" alt="Animation of cleaning route" style="width: 98%; height: auto;">
    </div>
    <figcaption style="text-align: center;">Animation of cleaning route</figcaption>
  </figure>
</div>

<hr style="border: none; border-top: 1px solid rgba(0, 0, 0, 0.1); margin: 20px 0;">

 <!-- {% include base_path %} -->

<!-- {% for post in site.research reversed %}
  {% include archive-single.html %}
{% endfor %} -->

<!-- We formulate the problem as a longest path problem in a well-structured graph. However, since collection directly impacts future plastic density, the corresponding edge lengths are non-linear polynomials. After analyzing the structural properties of the edge lengths, we propose a search-and-bound method, which leverages a relaxation of the problem solvable via dynamic programming and clustering, to efficiently find high-quality solutions (within 6%-optimal in practice), and develop a tailored branch-and-bound strategy to solve it to provable optimality. -->