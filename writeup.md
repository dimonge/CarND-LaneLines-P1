# **Finding Lane Lines on the Road**

## Introduction

For self-driving car to know where the lanes are on the road, It will need to be able to view the environment. Companies has developed hardware to provide a means for these.

In this project, I will provide the pipeline function for detecting lane line on the road in provided images and videos.

---

## **Finding Lane Lines on the Road**

The steps used to find the lanes are as follows:

* Transform the images using Grayscale transform.
* Blurring the images.
* Detection the edges using Canny edges transform.
* Find the area of interest (lanes region).
* Apply Hough transform to detect the lanes.
* Extrapolating the lines from the hough transformed images.
* Apply the extrapolated lines to the original images.

---

### Pipeline

I started by transforming the images using the grayscale transform function to convert the images to one color (gray color). Then I applied the Gaussian Noise kernel to blur the images.

![gray image] (./gray_result/output_whiteCarLaneSwitch.jpg)

Then I extracted the edges in the images using the Canny edges transform. Canny Edges transform is used to detect the edges in images.

![edges image] (./edges_result/output_whiteCarLaneSwitch.jpg)

Now, the images shows only lines which makes it easy to identify the area of interests (using region_of_interest()) in the image.

![region_of_interest] (./region_of_interest_result/output_whiteCarLaneSwitch.jpg)

Hough transform function is applied to the images to draw the hough lines.

![hough line] (./images_with_lanes_lines_before_extrapolation/output_whiteCarLaneSwitch.jpg)

To extrapolate to line segments, we separate the lines into groups of positive and negative gradient, then taking the average of the intercept and gradient value. Then we get the lanes lines from the output.

![hough line] (./result/output_whiteCarLaneSwitch.jpg)

### Identify potential shortcomings with your current pipeline


After testing the pipeline on the optional challenge videos (video where the driver was driving through a bend), the extrapolated line segments couldn't detect the line when the car was in the curve.  


### Suggest possible improvements to your pipeline

Improving the hough transform function to better work with various kind of the roads shapes.
