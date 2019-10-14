# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I apply blurr to images, after that I use canny to find edges in images, the next thing that I used is mask, I apply to image mask of interest, and after all I apply hough transform to find lines in images. 

In order to draw a single line on the left and right lanes, I modified the hough_lines() function by groupping finded by cv2.HoughLinesP lines into two groups by the slope (if slope > 0 it is right line and if slope < 0 it is left line) and finding start and end of the line by finding min and max X in lines and use max and min Y from the mask of interest. After that I use np.poly1d to find equations of the lines and draw them by the given  draw_lines function.

If you'd like to include images to show how the pipeline works, here is how to include an image: 




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what finded lines will interesect each other if the line on road image will strong curl. 

Another shortcoming could be that if shadow will lie on the landmark line my pipeline would not find lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to is to use dynamic mask of interest.

Another potential improvement could be to use perspective transform to find line curvature.
