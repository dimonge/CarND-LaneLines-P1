#**Finding Lane Lines on the Road**

##Introduction

For self-driving car to know where the lanes are on the road, It will need to be able to view the environment. Companies has developed hardware to provide a means for these.

In this project, I will provide the pipeline function for detecting lane line on the road in provided images and video.


---

**Finding Lane Lines on the Road**

The steps used to find the lanes are as follows:

* Transform the images using Grayscale transform.
* Blurring the images
* Detection the edges using Canny edges transform.
* Find the area of interest (lanes region).
* Apply Hough transform to detect the lanes
* Extrapolating the lines from the hough transform.
* Apply the extrapolated line to the original images.

---

### Pipeline

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

I started by transforming the image using the grayscale transform function to convert the image to one color. Then we applied the Gaussian Noise kernel to blur the images.

![gray image]({{site.baseurl}}/./gray_result/output_whiteCarLaneSwitch.jpg)

Then I extract the edges in the images using the Canny edges transform. Canny Edges transform is used to detect the edges in an image.

![edges image]({{site.baseurl}}/./edges_result/output_whiteCarLaneSwitch.jpg)

Now, the images shows only lines which makes it easy to identify the area of interests (using region_of_interest()) in the image.

![region_of_interest]({{site.baseurl}}/./region_of_interest_result/output_whiteCarLaneSwitch.jpg)

Hough transform function is applied to the images to draw the hough lines.

![hough line]({{site.baseurl}}/./result/output_whiteCarLaneSwitch.jpg)

To extrapolate to line segments,

###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ...

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
