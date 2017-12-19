# **Finding Lane Lines on the Road** 

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

My pipeline consisted of 5 steps. 

1. Remove irrelevent content by color-based (white and yellow) thresholding.

2. Convert to grayscale.

3. Gaussian blur 

4. Canny edge detection

5. Hough Line detection

6. Draw lines


In order to draw a single line on the left and right lanes, I modified the draw_lines() function by grouping the left and right lines by the sign of $\theta$ in the Hough coordinate. Within each group, the averaged values of $\theta$ and $r$ are computed to identify the line, which is then extrapolated to the ends of the region of interest.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lines are very curvy.

Another shortcoming could be the change of the line color due to weather or light conditions.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to standardize the brightness of the image before processing.

Another potential improvement could be to have the tunnable parmaeter adaptive to the image quality and light conditions.
