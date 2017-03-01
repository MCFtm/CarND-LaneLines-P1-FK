#**Finding Lane Lines on the Road** 

##Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work in a written report

[//]: # (Image References)

[image1]: ./test_images/solidWhiteCurve_res.jpg "Result after processing of the pipeline"

---

### Reflection

###1. Short description of the pipeline

The pipeline identify lane lines on the road both by images and videos. The result is achieved by
processing the images and videos in several steps by tools of computer-vision in order to filter,
identify and highlight lane-line-markings

My pipeline consisted of 7 steps. First, images are converted to grayscale, blurred by Gaussian-Kernel.
In the next step edges in the images/videos are detected by Canny-engine. As we have the road and lane-
markings always in a certain area of the image, the pipeline is designed to only consider relevant edges
that are derived from lane-lines. This is done by overlaying a mask that eleminates areas of the image
that are not relevant. By Hough-Transformation the resulting edges are transformed to lines. In the next
step the lines are separated by their left and right-position relative to the drivers perspective. Finally
the lines which are only segments and thus do not cover the complete lanes-lines are "connected" and
extrapolated.


![alt text][image1]


###2. Potential shortcomings with the current pipeline

One potential shortcoming would be that only straight lines are detected.

Another shortcoming could be that the processing time is probably too long for a realtime application


###3. Suggest possible improvements to your pipeline

A possible improvement would be to machine learning algorithms that generate features to detect lane lines.

Another potential improvement could be to finetune the parameters of the CV-processes applied in the pipeline.