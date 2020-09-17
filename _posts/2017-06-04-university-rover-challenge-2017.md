---
layout: project_post
title: "Mars Rover 2017"
date: 2017-06-04
thumbnail_image: /data/images/rover2017/thumb.jpg
---

I was extensively involved in the University of Waterloo Robotics team as an undergraduate student. The main project I worked on was a Mars rover for the University Rover Challenge. It is an annual competition held at the Mars Desert Research Station (MDRS) in Hanksville, Utah. The competition simulates the environment on Mars. The rover must finish a series of challenging tasks such as collecting and testing samples, traversing terrain autonomously, servicing equipment, and assisting astronauts. It was the first year our new team entered the competition and we were placed 15th out of 36 teams.

<div class="row">
<div class="col-md-8" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/group_us.jpg">
    <figcaption class="figure-caption">Our team at the competition</figcaption>
</div>
</div>
</div>

I was a core member of the team, leading mechanical, autonomy, and system integration work on the rover. In addition, I was also involved in the finance and recruitment efforts for the team.

As a mechanical lead, I led the mechanical team to design the rover chassis, manipulator module, soil sampling module, and the pan-tilt camera system. The chassis design was inspired by the Canadian Space Agency’s lunar rover. It uses a rocker design that allows wheels at each side of the rover to be at different angles to maximize contact with the ground surface. The manipulator module used worm gear design at all joints so that the arm would draw no power from the battery when holding steady.

<div class="row">
<div class="col-md-6" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/rover_chassis_arm_cad.png">
    <figcaption class="figure-caption">Rover chassis and arm CAD assembly</figcaption>
</div>
</div>
</div>

<div class="row">
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/chassis.gif">
    <figcaption class="figure-caption">Rocker chassis</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/end_effector.gif">
    <figcaption class="figure-caption">End effector</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/2dof_joint.gif">
    <figcaption class="figure-caption">2-DOF joint using differential</figcaption>
</div>
</div>
</div>


New to the 2017 rover challenge is the autonomous terrain traversal task. The rover is required to autonomously travel between tennis balls marked by GPS coordinates without any human intervention. Our design used an Extended Kalman Filter to fuse IMU, odometry, and GPS measurements to keep track of where we are. A trajectory rollout local planner was used to ensure the rover stays on the path to the next waypoint. With our design, we were among the top 4 highest scoring teams for this task.

<div class="row">
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/equipment.jpg">
    <figcaption class="figure-caption">Servicing equipment</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/astronaut_assist.jpg">
    <figcaption class="figure-caption">Astronaut assistance</figcaption>
</div>
</div>
<div class="col-md-4">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/traversal.jpg">
    <figcaption class="figure-caption">Autonomous traversal</figcaption>
</div>
</div>
</div>

<br>

<div class="video-responsive">
<iframe width="1905" height="756" src="https://www.youtube.com/embed/ak18WfTnooE"
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

<div class="row">
<div class="col-md-12" style="float: none;margin: 0 auto;">
<div class="mbr-figure" style="width: 100%;">
    <img src="/data/images/rover2017/group_all.jpg">
    <figcaption class="figure-caption">Competition group photo</figcaption>
</div>
</div>
</div>