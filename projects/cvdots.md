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
My workflow begins with raw 400x magnification images of the carbon nanoparticles. The first step is to convert the image to grayscale to prepare it for edge detection.

<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/01_raw.png" class="img-thumbnail" >
  <img width="250px" src="/img/cvdots/02_grayscale.png" class="img-thumbnail" >
</div>

Next, an edge detection algorithm is applied. While several methods like Sobel and Prewitt were considered, the Canny edge detector proved most effective. The nanoparticle images contain many "soft edges," and Canny's use of hysteresis thresholding was crucial for producing cleaner edge maps with fewer artifacts. I performed hyperparameter tuning to optimize the Canny filter, resulting in clearer boundaries for the subsequent steps.

<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/03_canny.png" class="img-thumbnail" >
  <img width="250px" src="/img/cvdots/04_canny_optimized.png" class="img-thumbnail" >
</div>

With a clear edge map, a Hough Transform is used to detect circular shapes. This transform identifies potential circles based on the detected edges. However, the Hough Transform alone cannot distinguish between the inner edges of the nanoparticles and the outer boundary of the fused cluster.

<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/05_hough.png" class="img-thumbnail" >
</div>

To isolate the individual nanoparticles, a filtering step is required. I implemented a method that evaluates each detected circle against the original grayscale image. Circles that do not cover a sufficient number of dark pixels (corresponding to the nanoparticles) are discarded. This effectively removes the exterior circles and leaves only those representing the individual particles. The radii of these final circles are then averaged to determine the mean particle size.

<div class="text-center p-4">
  <img width="250px" src="/img/cvdots/06_interior_circles.png" class="img-thumbnail" >
</div>
