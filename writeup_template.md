# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian Blur. After that I used the Canny Edge Detector to find all edges in the image. Next, I used a region-of-interest mask to select only certain edges that are of interest. Later I used the Hough Transform on the edges of interest in the ROI. I postulated that the lanes would form two straight lines one with a positive slope and another with a negative slope. I set a threshold on the slope to reject those Hough Lines that have very low slope. Then I collected all the positive slope lines and negative slopes into two different sets. I then fit a straight line using the end points of all positive slope lines and negative slope lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by simplifying the Hough Lines into two straight lines. 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the car is negotiating a turn.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to fit higher order polynomial curves instead of turns.
