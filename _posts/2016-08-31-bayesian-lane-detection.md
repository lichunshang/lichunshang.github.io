---
layout: project_post
title: "Lane Detection"
date: 2016-08-31
thumbnail_image: /data/images/ulma/thumb.png
---

I worked on this project for my internship at Waterloo Autonomous Vehicles Laboratory (WAVE) Lab. I was helping a Master’s student with implementing his research results on lane detection, transferring MATLAB code to C++ for real-time testing. The lane detection pipeline uses a stereo camera to improve results. The pipeline is as follows:

1. use stereo camera to remove any parts of the image not on the ground plane
2. Convert camera image into bird's eye view (BEV)
3. use a Neural Network to look at a patch of the image and classify each pixel as the lane marking or not
4. Extract line segments out of the image
5. Using RANSAC, generate lane marking hypothesis by fitting cubic splines to the line segments, null hypothesis is also added to indicate no lane marking
6. Evaluate each hypothesis using Bayesian probability on various metrics
7. The best result is chosen to be correct

At the end of the project, we also went to Detroit and demoed the results live on the road. The video below shows the results on the Waterloo dataset.

<div class="video-responsive">
<iframe width="1905" height="756" src="https://www.youtube.com/embed/tBPPhn14g1M" 
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>