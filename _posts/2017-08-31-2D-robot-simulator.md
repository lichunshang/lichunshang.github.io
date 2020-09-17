---
layout: project_post
title: "2D Robot Simulator"
date: 2017-08-31
thumbnail_image: /data/images/flatland/thumb.jpg
---

I worked on this project while doing an internship at Avidbots. Avidbots is a company that produces fully autonomous commercial floor cleaners. To ensure systems are working correctly, it was constantly tested in simulated environments. The 3D simulator that was too computationally expensive for the need to simulate a floor cleaner. The 3D simulator would suck up all resources available on a server, which allows at most two simulations can be executed at the same time. The project is to implement a 2D simulator for faster simulation.

The simulator is built using the Box2D physics engine which is commonly used in games such as Angry Bird. It is integrated directly with the Robot Operating System (ROS). The simulation environment and its objects are configured through YAML. A plugin system is provided for users to define custom behaviours. Default plugins are also provided which include simulating laser, bumper sensors, and various drive systems.

<div class="row">
<div class="col-lg-15">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/flatland/demo.gif">
    <figcaption class="figure-caption">Example of Flatland in action, a tricycle drive robot with a front facing 2D Lidar.</figcaption>
</div>
</div>
</div>

The project is open-source, and it can be found
<a href="//github.com/avidbots/flatland">here</a>.