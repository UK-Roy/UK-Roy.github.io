---
layout: page
title: IHABOT — Intelligent Hospital Assistance Robot
description: Autonomous medical assistive robot developed to minimize direct doctor–patient contact in hospital environments during contagious disease outbreaks
category: research
order: 4
year: 2021 - 2022
role: Research Assistant
organization: Centennial Research Grant, University of Dhaka
preview: ihabot.png
report: https://drive.google.com/file/d/1BI4GVFCr5P-X8KBTSn49NESsbN0KPgVu/view?usp=drive_link
video: https://drive.google.com/file/d/1b-JXv2Bz7If3wSBjo9QHkDR-wD9Vo62I/view?usp=sharing
---

## Objective
The objective of this project was to design and develop an autonomous medical assistive robot capable of safe and reliable operation in hospital environments, with the goal of minimizing direct doctor–patient contact during contagious disease outbreaks. Emphasis was placed on robust autonomous navigation, system reliability in real-world clinical settings, and practical deployment to support healthcare professionals while reducing the risk of disease transmission.

## My role
- Led autonomous navigation stack development
- Implemented navigation + perception for indoor medical environments
- Integrated health-monitoring sensors for real-time patient data acquisition
- Developed an RGB-D sensing framework using Kinect v2 to acquire spatio-temporal 3D human skeletal joint data for exercise assessment

## Methods / Stack
- ROS(Noetic) Navigation Stack (planning, localization, obstacle avoidance)
- Sensor stack: LiDAR
- RGB-D–based skeletal joint data were processed using an ST-GCN to predict exercise performance scores

## Media
<div class="text-center">
{% include figure.liquid path="assets/img/project_preview/ihabot_design.jpeg" caption="Design of IHABOT" class="img-fluid rounded z-depth-1 w-75" zoomable=true %}
</div>

<figure class="figure text-center">
  <a href="https://drive.google.com/file/d/1TDzUrwhL7D6qM4a3UZmxt89KlB_KUAmg/preview" target="_blank" rel="noopener">
    <img
      src="{{ 'assets/img/project_preview/stgcn.png' | relative_url }}"
      class="img-fluid rounded z-depth-1 w-75 mx-auto d-block"
      alt="Exercise Assessment Video using STGCN"
    >
  </a>
  <figcaption class="figure-caption text-center">
    Exercise Assessment Video using STGCN <strong><span style="color:#b23bcf;">(To see the reults, please click in the image)</span></strong>
  </figcaption>
</figure>

## Links
- Report: [PDF]({{ page.report }})
- Video: [Demo]({{ page.video }})
