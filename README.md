# Project_1-Finding_Lane_Lines
Identify lane lines on the road

# **Finding Lane Lines on the Road** 

---

The major goal of this project is to make a pipeline that can identify road lane lines in some images or videos.
Starting from some sample images, the result will be the overlapping of the higlighted lines on the source images.


White Source Image               | White Output Image
:-------------------------:|:-------------------------:
![](/CarND-LaneLines-P1/test_images/WhiteOutputImage.png)


# **Pipeline** 
My pipeline consists of 7 steps:

1) Read the source raw image.
2) Convert the image into Gray Scale.
3) Canny Edge detection.
4) Draw the region of interest.
5) Hough Transformation.
6) Lines drawing
7) Overlapping of the two images.



### 1) Read the source raw image.

First of all, we have to upload the image.


### 2) Convert the image into Gray Scale.

Then we have to convert the image into a gray scaled image.



### 3) Canny Edge detection.

Canny Edge Detection is our way to find the edges on the image: using the color gradient, we can find the edges of the image where the pixel values are very different the one from the other.



### 4) Draw the region of interest.

When we are driving a car, only a part of the entire image is needed; we have to focus on the central portion of the image to indentify the lines.
To achieve this goal, we use a mask to select only a portion of the entire image. 


### 5) Hough Transformation.

Now that we have our interest area of the space, we use a Hough transofrmation in order to find the lines of the road.



### 6) Lines drawing

To draw the road lines we use an average and extrapolation of the points that we have selected.



### 7) Overlapping of the two images.

At the end the last step is to overlap the source image with the new one with our lines drawn to see if there is match between them.





### 2. Identify potential shortcomings with your current pipeline

   One potential shortcoming would be what would happen if  the road is all white (snow probably) and we are not aible to find the edges and the road lines.
  
   One more problem could be the bending radius of the road; increasing the turning of the road, we are not able to higlights the road lines in a perfect way.
  
### 3. Suggest possible improvements to your pipeline

  One idea could be the improvement of the lane finding not using only lines but even morre difficult curves.



