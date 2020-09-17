---
layout: project_post
title: "Stereo Visual Inertial Odometry"
date: 2018-12-20
thumbnail_image: /data/images/stereo_vio/thumb.png
---

We implemented a Visual Inertial Odometry (VIO) pipeline. Odometry is a subset of the Simultaneous Localization and Mapping (SLAM) problem. A full SLAM problem creates a map as the motion of the vehicle is estimated at the same time. The map can be used later for loop closures. In Odometry, we are only interested in estimating the ego-motion.

VIO is a very well studied field. It is widely understood that fusing acceleration and rotation rate measurements from Inertial Measurement Units (IMU) with vision produces more accurate results. This is especially true when the vehicle is under rapid motion. Although absolute scale can be recovered in monocular VIO, it requires the vehicle to be accelerating for scale to be observable, thus using stereo cameras increases accuracy and robustness. We also chose to implement a tightly coupled optimization approach which has been shown to yield better results.

For the visual part of the pipeline, point features are extracted from the image using from each frame and matched between the left and the right camera to triangulate their 3D position. We used ORB for feature extraction and descriptor. Once a feature point in the 3D space is observed across a few frames, it becomes a landmark. Frames that observe the same landmark are constrained geometrically through the camera projection model.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/stereo_vio/extracted_features.png">
    <figcaption class="figure-caption">Extracted features</figcaption>
</div>
</div>
</div>

IMU data arrives at ten times the frequency of the images. It would be incredibly inefficient if each IMU measurement is used individually in optimization, thus the IMU measurements are integrated between frames to provide a relative pose constraint. In addition, several math tricks are used to reduce the computational load.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/stereo_vio/bundle_adjust.png">
    <figcaption class="figure-caption">Optimized window of landmarks and IMU measurements</figcaption>
</div>
</div>
</div>

The landmarks and IMU constraints are formulated into a least-squares problem and optimized using Levenberg-Marquardt. The optimization is performed over a sliding window to bound the computational time. We demonstrated our VIO pipeline on the EuRoC drone dataset and it works better than using vision alone. Our report can be downloaded <a href="/data/docs/stereo_vio.pdf">here</a>.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/stereo_vio/test_platform.jpg">
    <figcaption class="figure-caption">Drone used in the EuRoC dataset</figcaption>
</div>
</div>
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/stereo_vio/mh01_results.png">
    <figcaption class="figure-caption">Results from one set of data</figcaption>
</div>
</div>
</div>

<br>