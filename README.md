CUDA Introduction
=================

**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 1**

* Sally Kong
* Tested on: Windos 8, i7-5500U CPU @ 2.40GHz 2.40 GHz, GEForce 920M (Personal)

## N-body Simulation Screen Capture
![](images/Screenshot - NBody.png)

## Performance Analysis

* Parts 1 & 2: How does changing the tile and block sizes affect performance?
  Why?
For part 1, reducing the block sizes reduced the fps, but for part 2, reducing the block sizes didn't have an affect on the performance. This is because for part 2, we only did matrix multiplications of 5x5 matrices which don't require a lot of threads as much as the N-body simulation in part 1 which dealt with over 5000 elements. <br />

* Part 1: How does changing the number of planets affect performance? Why?

Having more planets lowers the fps because there are more computations to be done for every planet for every additional planet. Below are the observed fps for simulations with different numbers of planets and with/without the visualization.

With Visualization: <br />
N = 5,000 -> ~50fps <br />
N = 10,000 -> ~14fps <br />
N = 20,000 -> ~4.2fps <br />
N = 50,000 -> ~0.7fps <br />

Without Visualization: <br />
N = 5,000 -> ~60fps <br />
N = 10,000 -> ~15fps <br />
N = 20,000 -> ~4.2fps <br />
N = 50,000 -> ~0.7fps <br />

* Part 2: Without running comparisons of CPU code vs. GPU code, how would you
  expect the performance to compare? Why? What might be the trade-offs? <br />

I would expect the performance in the GPU to be faster because GPUs are optimized for parallel computations, and matrix addition, subtraction or multiplication are "embarrassingly parallel" operations. However, apotential trade-off / bottleneck would be with memory transfer from device-to-host and host-to-device for smaller matrices.
