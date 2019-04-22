# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on the work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My Pipeline function identify_lanes follows following step
1. Creates a copy of the image to work on
2. Converts the image to grayscale
3. Removes Gaussian noise from the image
4. It generates the Canny Image
5. Identifies the area/region of Interest
6. Generates Probability based Hough lines.
7. Finally, it creates a weighted image.
.... 

In order to create a single line segment I modified the draw line function to perform following actions
1. Identify the Ymax and Ymin on the vertical axis.
2. Segregate the lines based on positive and negative slope. Line on the left will have a positive slope whereas line to the right will have a negative slope.
3. Calculate Weighted Average for the slope and line constant. Here square distance of the line segment is used as the weight.
4. Fit YMax and YMin on the identified line to obtain corresponding X coordinate.
5. Plot the calculated coordinates 


### 2. Identify potential shortcomings with your current pipeline

The pipeline assumes a region of interest. For every installation, Region of interest would have to be adjusted.


### 3. Suggest possible improvements to your pipeline

The pipeline function could be more robust to make region of interest more configurable
