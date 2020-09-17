---
layout: project_post
title: "Stereo Camera System for ADAS"
date: 2017-04-02
thumbnail_image: /data/images/fydp/thumb.png
---

We designed a prototype stereo camera system that provides depth information for use in Advance Driver Assistance Systems(ADAS) for our capstone project.

Assuming perfect matching between the stereo images, accuracy in stereo systems decreases quadratically with distance due to the fact that the pixels are discrete. In addition, distance can only be triangulated in the regions of the image where two cameras have an overlapping field of view. Accuracy can be increased in two ways: increase the baseline distance between two stereo cameras or decrease the cameras’ field of view (FOV). Both of these decrease the overlapping region, thus increasing the minimum distance where detection is possible.

<div class="row">
<div class="col-md-6" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/baselines.png">
    <figcaption class="figure-caption">Hardware setup of our system</figcaption>
</div>
</div>
</div>

We attempted to solve this problem by using a duo-baseline setup with three cameras. One baseline is between the outermost cameras at a distance of 0.6 meters, which provides the greater accuracy, but it only works at longer distances. The other baseline is 0.2 meters between the two cameras on the left which can be used for close range. We chose 1.3MP USB3 global shutter cameras from Point Grey, and an NVIDIA Jetson TX1 for processing. In addition, we designed custom PCBs for supplying power and provide hardware synchronization for the cameras.

<div class="row">
<div class="col-lg-12">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/in_car_setup.png">
    <figcaption class="figure-caption">Setup for in-car testing</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/c_lot_left.png">
    <figcaption class="figure-caption">Left camera image</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/c_lot_mid.png">
    <figcaption class="figure-caption">Middle camera image</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/c_lot_right.png">
    <figcaption class="figure-caption">Right camera image</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-md-6" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/fydp/c_lot_depth.png">
    <figcaption class="figure-caption">Final depth</figcaption>
</div>
</div>
</div>

The camera system is calibrated for lens distortions as well and the position and orientations between cameras. Then, stereo images from two baselines are matched to generate a depth image. We selected Semi-Global Matching (SGM) on the Jetson TX1 GPU for stereo matching. SGM offers a good trade-off between speed and accuracy. Finally, depth from the two baselines are fused according to their optimal distances.

We tested the stereo camera system on a car by mounting it behind the windshield and drove the car around the university. Note that the project focused on generating depth information, the car and pedestrian detections were added last minute addition to demo how the depth information could be used, and thus there are lots of false detection. The depth results are not very good around the edges due to calibration and cheap low quality lens ($7 each) we used.

<div class="video-responsive">
<iframe width="1905" height="756" src="https://www.youtube.com/embed/QeNomStHLy8"
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>