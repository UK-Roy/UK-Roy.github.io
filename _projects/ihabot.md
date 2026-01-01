---
layout: page
title: IHABOT — Intelligent Hospital Assistance Robot
description: Navigation stack + embedded health sensor integration for real-world hospital robotics.
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
Develop an assistance robot platform for indoor hospital environments, focusing on autonomous navigation and patient-support features.

## My role
- Led autonomous navigation stack development
- Implemented navigation + perception for indoor medical environments
- Integrated health-monitoring sensors for real-time patient data acquisition
- Applied ML models on physiological sensor data for decision support

## Methods / Stack
- ROS/ROS2 navigation (planning, localization, obstacle avoidance)
- Sensor stack: LiDAR/camera/IMU (as applicable)
- Embedded integration for vitals acquisition

## Results (high-level)
- Real/Sim test summary (routes, stability, success rate)
- Key improvements over iterations

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
    Exercise Assessment Video using STGCN <strong><span style="color:#b23bcf;">(For see the reults, please click in the image)</span></strong>
  </figcaption>
</figure>

## Links
- Report: [PDF]({{ page.report }})
- Video: [Demo]({{ page.video }})
