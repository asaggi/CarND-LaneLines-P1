# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./out_images/gray.png "Grayscale"
[image2]: ./out_images/canny.jpg "Canny"
[image3]: ./out_images/edgesLeft.jpg "edgesLeft"
[image4]: ./out_images/edgesRight.jpg "edgesRight"
[image5]: ./out_images/houghLeft.jpg "houghLeft"
[image6]: ./out_images/houghRight.jpg "houghRight"
[image7]: ./out_images/out_solidYellowLeft.jpg "out_solidYellowLeft"


### Reflection

### 1. Pipeline description

#### My pipeline consisted of 5 steps . 
##### 1 Convert images to grayscale . 
 ![alt text][image1] . 
##### 2.  Apply Canny edge detection on the output . 
 ![alt text][image2]
##### 3.  Identify region of interest . 
  - Left Side . 
 ![alt text][image3]
  - Right Side . 
 ![alt text][image4]
##### 4. Apply hough transform on the region of interest . 
 ![alt text][image5]
 ![alt text][image6]
##### 5. Identify the line markings and merge line markings and the original image . 
 ![alt text][image7]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by getting the top and bottom coordinates of the end points of a line segment from huff transform. Then using these coordinates to draw lines for these coordinates

### 2. Identify potential shortcomings with your current pipeline

We can have a lot of load on the system with image processing per frame
We are using very restrictive region of interest, which might vary with various road conditions

### 3. Suggest possible improvements to your pipeline

A variable region of interest, which can be more flexible in order to identify regions
