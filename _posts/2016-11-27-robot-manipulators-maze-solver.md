---
layout: project_post
title: "Robot Maze Solver"
date: 2016-11-27
thumbnail_image: /data/images/me547/thumb.jpg
---

We implemented a fully automated method for accurate maze solving for a 4th-year course. The system used
a camera looking from above the workspace and a FANUC robotic arm holding a marker.

A binary representation of the maze is extracted using image processing techniques
such as cropping, thresholding, noise reduction, and contour finding. The start
point of the maze is marked by a square and the endpoint is marked by a triangle.

<div class="row" style="margin-bottom: 0.75rem">
<div class="col-md-5">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/maze_input.png">
    <figcaption class="figure-caption">Input from the camera</figcaption>
</div>
</div>
<div class="col-md-5">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/maze_result.jpg">
    <figcaption class="figure-caption">Binary image with end points identified</figcaption>
</div>
</div>
</div>

To ensure the path travels down the center, the binary image is skeletonized and a weighted A* algorithm is used to find a path through the maze. A greedy algorithm is then applied to reduce the number of waypoints required to traverse the path.

<div class="row">
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/skeleton.jpg">
    <figcaption class="figure-caption">Skeletonized</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/a_star.gif">
    <figcaption class="figure-caption">A*</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/wp_reduce.gif">
    <figcaption class="figure-caption">Reduce waypoints</figcaption>
</div>
</div>
</div>

In order for the robotic arm to draw accurately to the designated path, we calibrated the position and orientation of the camera, robotic arm, and the table surface. We place a standard checkerboard at a known location on the work surface, and then use homography to find the transformation between the checkerboard and the camera.


<div class="row">
<div class="col-md-5">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/me547/transformations.png">
    <figcaption class="figure-caption">Transformations</figcaption>
</div>
</div>
</div>

<br>

<div class="video-responsive">
<iframe width="1905" height="756" src="https://www.youtube.com/embed/BHMZt-DtL1Q"
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

<br>

<div class="video-responsive">
<iframe width="1905" height="756" src="https://www.youtube.com/embed/vXIrs3m8RJQ" 
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>