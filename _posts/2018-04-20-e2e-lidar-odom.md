---
layout: project_post
title: "Deep Learning Lidar Odometry"
date: 2018-04-20
thumbnail_image: /data/images/nn_lidar/thumb.jpg
---

Traditional Lidar Odometry is incredibly difficult due to factors such as motion distortion, occlusions, laser beam divergence, and other factors. Instead of manually modelling these difficult scenarios, data-driven methods such as deep learning can be used.

The idea stemmed from a paper published in The International Journal of Robotics Research (IJRR) [1]. In this paper, they used a convolutional-recurrent neural network architecture to learn visual odometry. The architecture allows the network to learn system dynamics and propagate states through multiple time steps. We modified this architecture for Lidar Odometry.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/network_arch.png">
    <figcaption class="figure-caption">Our network architecture</figcaption>
</div>
</div>
</div>

We obtained Lidar data from the KITTI dataset which uses a 64 beam Velodyne Lidar. The Lidar data is preprocessed into images. Each row of the image ecnodes a single laser beam, and each column encodes different azimuth angle. The distance and intensity data are stacked as two channels of an image. The sequence of images are passed into the network, and at the output are Lidar poses. The details regarding this project can be seen in the <a href="/data/docs/end-end-lidar.pdf">report</a>.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/camera_image.jpg">
    <figcaption class="figure-caption">Camera image of the scene</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-md-6" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/lidar_pointcloud.jpg">
    <figcaption class="figure-caption">Lidar pointcloud of the scene</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-lg-12" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/lidar_distance.jpg">
    <figcaption class="figure-caption">Lidar distance image</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-lg-12" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/lidar_intensity.jpg">
    <figcaption class="figure-caption">Lidar intensity image</figcaption>
</div>
</div>
</div>

The network is trained with frame to frame loss as well as loss for a sub-sequence. The network is able to converge and some of the odometry results can be seen below. The results are not as good as some of the classical methods such as LOAM [2], but we showed that neural networks are capable of estimating odometry from Lidar and we are excited to keep improving our results.

<div class="row">
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/03.jpg">
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/06.jpg">
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/nn_lidar/07.jpg">
</div>
</div>
</div>

<br>

[1] S. Wang, R. Clark, H. Wen, and N. Trigoni, “End-to-end, sequence- to-sequence 
probabilistic visual odometry through deep neural net- works,” 
The International Journal of Robotics Research, vol. 0, no. 0, p. 0278364917734298, 0.

[2] J. Zhang and S. Singh, “Loam: Lidar odometry and mapping in real- time,” 
in Robotics: Science and Systems Conference, July 2014.