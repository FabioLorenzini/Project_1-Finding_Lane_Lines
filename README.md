# Project_1-Finding_Lane_Lines
Identify lane lines on the road

# **Finding Lane Lines on the Road** 

---

The major goal of this project is to make a pipeline that can identify road lane lines in some images or videos.
Starting from some sample images, the result will be the overlapping of the higlighted lines on the source images.


White Source Image               | White Output Image
:-------------------------:|:-------------------------:

![](./test_images/solidWhiteRight.jpg) |  ![](./image_output/yellow.gif)

# **Pipeline** 
My pipeline consists of 8 steps:

1) Read the source raw image.
2) Convert the image into Gray Scale.
3) Canny Edge detection.
4) Draw the region of interest.
5) Hough Transformation.
6) Line drawing
7) Overlapping of the two images.
8) Output testing.



### A) Read/Upload the image to be processed

First step is to upload the image that has to be processed.

->![Starting image](./image_output/starting.png)<-

### B) Conversion into Gray Scale (cv library)

Once the image is uploaded, it is converted to a gray scaled one to start highlighting the pixel gradients.

->![Gray scaled image](./image_output/grayscale.png)<-

### C) Canny Edge detection in order to higlight edges.

Canny Edge Detection is based on gradient, meaning how fast are x and y changning. It is expected to find edges where pixel values change rapidly (road lines).

->![Edge Detected](./image_output/edge.png)<-

### D) Define a polynomial region of interest (where to find lane lines).

In an image, only a region of interest has to be taken into account, where our lines will be. For this reason, a mask is created in order to higlight edges where required.

->![Edge Masked](./image_output/edgemasked.png)<-

### E) Hough Transformation in order to identify points building a line.

A transofrmation into the Hough Space is then performed in order to find the line that pass through all the points that a re making a line.

->![Hough Transofrmation](./image_output/houghtransform.png)<-

### F) Line drawing

Once the line are highlightes, an average and extrapolation of their points is performed in order to draw the road lines.

->![Road Lines Drawn](./image_output/linedrawn.png)<-

### G) Overlay of the two images (lines detected + original image).

Last part of the pipeline is to overlay the starting image with the one with the lines drawn.

->![Images overlayed](./image_output/finalimage.png)<-

### H) Output testing.


### 2. Identify potential shortcomings with your current pipeline

  A) One potential shortcoming would be what would happen when the line curvature increase, since the line drawing is thought       just for straight lines.

  B) Another shortcoming could be the region of interest, since it is focused on the horizon and not to the ideal line of           vision of the driver. This would lead to a similar behavior as highlighted before.
  
### 3. Suggest possible improvements to your pipeline

This is related to the points highlighted in the previous section: 

  A) A possible improvement would be to develop a smarter line fitting, including polynoms greater thatn 1 grade in order           to have a good curvature representation.

  B) Another potential improvement could be to improve the region if interest so that it follows the driver line of vision         on the road



