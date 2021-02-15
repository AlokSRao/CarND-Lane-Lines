# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./examples/grayscalefalse.png "Grayscale False Color"
[image3]: ./examples/Gaussblur.png "Gaussian Blur"
[image4]: ./examples/CannyEdge.png "Canny Edge Detection"
[image5]: ./examples/mask.png "Mask Applied to Edge Image"
[image6]: ./examples/Hough.png "Hough Transform"
[image7]: ./examples/FinalOutput.png "Fianl Composite Image"
[image8]: ./examples/params.png "Grayscale"

---

## Reflection

## Pipeline
### 1. Convert image to greyscale

The image/frame is converted to greyscale because it is easier to enable Canny edge detection on
greyscale images. A copy of the image is saved for future use.

![alt text][image1]

Here is the grayscale image with false colors.

![alt text][image2]

### 2.  Smoothen image
The image frame is next smoothened with a gaussian filter for noise reduction.

![alt text][image3]


### 3.  Canny Edge Detection

The image is next convoluted with a canny filter to figure out the gradient of the image. This ill detect all
the lines.

![alt text][image4]


### 4.  Canny Edge Detection

Assuming the camera is in a fixed position, we can crop out the area that is not of interest. This helps to
remove unnecessary edges detected.

![alt text][image5]

### 5.  : Hough transform

Hough transform works by converting lines from x-y space into parameterized space. In the
parameterized space, we can use polling to figure out which lines pass through most points in the
detected image.

![alt text][image6]


### 6.  :  Overlay with original image

Combine the above image with original images for better visualization.

![alt text][image7]

### 7.  :  Parameters used


![alt text][image8]

## Shortcomings

This algorithm will not work on curved lines, and any situation where the lines appear curved (such as
going downhill, camera warping etc.). The edge detection is also not very robust and there is a lot of
tradeoff between edge detection and noise.


## Output Video

Here's a [link to my video result](./test_videos_output/solidWhiteRight.mp4)
