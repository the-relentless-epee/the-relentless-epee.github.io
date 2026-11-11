---
title: "BLDC Virtual Cartesian Spring"
summary: "A 2-DOF robot arm that simulates a virtual spring and slider"
thumbnail: /assets/images/projects/bearing-fixture.svg
order: 2
math: true
---

# Overview:

This is a quick project to learn FOC control theory and Jacobian-based robotics kinematics. I was inspired by [this video](https://www.youtube.com/watch?v=rFSXDaZQ4Qo) and wanted to make something similar.

My goal is to have a robot arm whose end-effector behaves like a linear slider attached to a spring. I first made a simple 2-DOF planar serial link manipulator using some BLDC gimbal motors, then worked out the math (relatively simple for 2DOF. more than 2 DOF is a different story...) to translate an arbitrary force vector in $$\mathbb{R}^2$$ into a joint torque vector (also in $$\mathbb{R}^2$$ because it only has two motors)fdafda

