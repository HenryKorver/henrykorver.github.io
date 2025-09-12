---
layout: project
type: project
image: img/cotton/cotton-square.png
title: "Carbon Nanoparticle Analysis"
date: 2023
published: true
labels:
  - Python
  - cv2
  - Computer Vision
  - Nanodots
summary: "I developed a sizing algorithm for clusters of fused carbon nanodots by using existing computer vision tools in tandem."
---

This portfolio presents my work from spring 2023 on the analysis of carbon nanoparticles. These materials are a subject of significant research due to their wide-ranging applications in fields like drug delivery, bioimaging, and energy storage. My project focused on addressing a key challenge in this research: the manual, time-consuming nature of analyzing microscopy images of these materials.

### The Project: Automation through Computer Vision
The core of my work involved developing an automated image processing workflow to characterize carbon nanoparticles. I used methods inspired by a study from Meng et al., combining a Hough-Transform based circle detection method with Canny-edge detection. This approach allowed for the determination of the average size of fused particles within an image.

My contribution to this methodology was its successful application to images with a significantly higher degree of particle overlap, a common and difficult problem in material science. This project demonstrates the practical application of computer vision and algorithmic analysis to streamline data characterization in material science research.

### Image Processing Workflow
My workflow begins with raw 400x magnification images of the carbon nanoparticles.
<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/01_raw.png" class="img-thumbnail" >
</div>
The image is then converted to grayscale and a Canny edge detection filter is applied. I optimized the hysteresis threshold to obtain clearer boundaries.
<div class="text-center p-4">

  <img width="250px" src="/img/cvdots/02_grayscale.png" class="img-thumbnail" >
  <img width="250px" src="/img/cvdots/03_canny.png" class="img-thumbnail" >
  <img width="250px" src="/img/cvdots/04_canny_optimized.png" class="img-thumbnail" >
</div>
A Hough transform is then used to detect circles from the edges.
<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/05_hough.png" class="img-thumbnail" >
</div>

To isolate the individual nanoparticles, a filtering step is required. I implemented a method that evaluates each detected circle against the original grayscale image. Circles that do not cover a sufficient number of dark pixels (corresponding to the nanoparticles) are discarded. This effectively removes the exterior circles and leaves only those representing the individual particles. The radii of these final circles are then averaged to determine the mean particle size.

<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/06_interior_circles.png" class="img-thumbnail" >
</div>
