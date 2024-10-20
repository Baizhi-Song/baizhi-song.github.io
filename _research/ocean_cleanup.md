---
title: "Optimizing the Path Towards Plastic-Free Oceans "
collection: research
type: "Talk"
permalink: /research/ocean_cleanup
layout: archive
# header:
#   teaser: /LBS-Logo.png
  # overlay_image: /01_TOC/TOC_system03.jpg
#   image: /LBS-Logo.png
#   header: /LBS-Logo.png
    # overlay_color: "#333333" 
    # overlay_filter: 0.1
author_profile: true
excerpt: "Increasing ocean plastic pollution is irreversibly harming ecosystems and human economic activities. We partner with The Ocean Cleanup and use optimization to help clean up oceans from plastic faster."

---

## Introduction

Our oceans are being threatened by growing and severe plastic pollution. Because of its environmental and economic relevance, the reduction of ocean pollution has been listed as an explicit target in the United Nations' [Sustainable Development Goal \#14 'Life Below Water'](https://sdgs.un.org/goals/goal14). To reduce the legacy floating ocean plastic, our NGO partner, [The Ocean Cleanup](https://theoceancleanup.com/) (TOC), developed a plastic cleaning system that includes a floating barrier dragged by two ships (see video below). The system moves slowly through the water to capture new plastic and needs to empty its retention zone (extraction) regularly. 
In our paper, we optimize the route and the extraction schedule of their plastic collection system in the ocean to maximize the quantity of plastic collected over time.

<div style="position: relative; padding-bottom: 39.375%; height: 0; overflow: hidden; max-width: 70%; margin: auto;">
  <iframe style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" src="https://www.youtube.com/embed/31gFN3vP_0g" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

## Graph-based model & path-dependency structure

In our problem, we discretize the space and time and model the routing and scheduling decisions as paths in a directed acyclic graph (DAG). Under this lens, the quantity of plastic collected can be seen as edge length in this graph and our problem as a longest path optimization problem. 
However, due to the direct impact of our routing decisions on future plastic density, our resulting optimization problem is a non-linear and non-decomposable longest path problem. 

In our paper, we formally analyze the structure of path-dependent edge lengths, which resembles structure arising in covering problems. We derive lower and upper bounds on the estimation error obtained when ignoring the path dependency, which will serve as the basis for our algorithmic strategy. 

<div style="text-align: center;">
  <img src="/images/01_TOC/path_dependency.gif" alt="Animation of cleaning route" style="max-width: 60%; height: auto;">
</div>


## Algorithms

With the analysis of the path-dependency structure, we propose a search-and-bound strategy to efficiently find a high-quality solution for this class of problems, with certificates of near-optimality. Our algorithm leverages a linear relaxation of the problem solvable via dynamic programming to efficiently search through the space of trajectories by combining geographical clustering with terminal values of the DP approach. 
We also propose a tailored branch-and-bound scheme to solve this class of problems exactly.

<!-- , using our search-and-bound algorithm as the root node analysis. On small instances (up to 3-day planning), our search-and-bound strategy finds an optimal solution, while scaling better with respect to the problem size than exact approaches. -->


<div style="text-align: center;">
  <img src="/images/01_TOC/path_demo_weather_2month_HD-ppt.gif" alt="Animation of cleaning route" style="max-width: 70%; height: auto;">
  <!-- <figcaption style="text-align: center;">Animation of a plastic cleanning route (ignore extraction)</figcaption> -->
</div>

## Numerical results

We evaluate the benefit of our search-and-bound algorithm on a one-year dataset of ocean weather conditions and plastic density. We find that our optimization approach yields at least a 60% improvement in terms of average collection efficiency compared with their current routing strategy. In particular, we observe greater benefits (+100%) during winter months, because weather conditions (and wave height in particular) are limiting the ability to extract, hence exacerbating the benefit of jointly optimizing the route and the extraction schedule. In addition, our algorithm allows The Ocean Cleanup to explore the non-linear impact of strategic system dimensioning decisions (e.g., span of the system and size of the retention zone). 

<div style="display: flex; justify-content: center; align-items: flex-start; margin-bottom: 10px;">
  <figure style="text-align: center; max-width: 50%; margin: 0;">
    <img src="/images/01_TOC/main_result_bar_avg_reward_clusterK_2024Apr04.jpg" alt="Our fantastic coauthor Yannick" style="width: 65%; height: auto;display: block; margin: auto;">
    <figcaption style="text-align: center;">Weekly quantity of plastic collected, for the benchmark and each of the optimization-based approach, averaged over the 13 simulations.</figcaption>
  </figure>
  <figure style="text-align: center; max-width: 50%; margin: 0;">
    <img src="/images/01_TOC/alpha_C25_23Aug.jpg" alt="Retention zone hauled on deck for emptying" style="width: 68%; height: auto;display: block; margin: auto;">
    <figcaption style="text-align: center;">Weekly plastic collection by optimization-based approach (Rolling) under different &alpha; (relates to the span), averaged over the winter and summer months.</figcaption>
  </figure>
</div>

## Conclusion


To reduce ocean plastic pollution, we collaborated with The Ocean Cleanup and improve the collection yield of their plastic collection system in the ocean. Specifically, we optimize the route of their plastic collection system to maximize the quantity of plastic collected over time. We formulated this problem as a longest path problem with non-linear polynomial edge lengths, and proposed a search-and-bound method to to efficiently find high-quality solutions. Our method effectively improve their collection effiency, and also informs the design of their next generation system.
Looking ahead, it is valuable to account for uncertainty in weather predictions and plastic dynamics. In particular, we are currently investigating whether collection of real-world data by drones or satellites could help quantify uncertainty and lead to robust versions of our longest path problem. 

<div style="display: flex; align-items: flex-start; margin-bottom: 10px;">
  <figure style="max-width: 50%; margin: 0;">
    <img src="/images/01_TOC/TheOceanCleanup-System03-Crew-Sorting-Plastic1.jpg" alt="Our fantastic coauthor Yannick" style="width: 90%; height: auto;">
    <figcaption style="text-align: center;">Our fantastic coauthor Yannick (right). Credit: <a href="https://theoceancleanup.com/media-gallery/">The Ocean Cleanup</a></figcaption>
  </figure>
  <figure style="max-width: 50%; margin: 0;">
    <img src="/images/01_TOC/TheOceanCleanup-System03-Second-Extraction-scaled.jpg" alt="Retention zone hauled on deck for emptying" style="width: 90%; height: auto;">
    <figcaption style="text-align: center;">Retention zone hauled on deck for emptying. Credit: <a href="https://theoceancleanup.com/media-gallery/">The Ocean Cleanup</a></figcaption>
  </figure>
</div>

<hr style="border: none; border-top: 1px solid rgba(0, 0, 0, 0.1); margin: 20px 0;">

**Paper:** 
- **Optimizing the Path Towards Plastic-Free Oceans**, Dick den Hertog, Jean Pauphilet, Yannick Pham, Bruno Sainte-Rose, and Baizhi Song (2024) [[Preprint]](https://optimization-online.org/2023/10/optimizing-the-path-towards-plastic-free-oceans/)
