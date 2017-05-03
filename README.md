# **Finding Lane Lines on the Road** 

When we drive, we use our eyes to decide where to go. The lines on the road that 
show us where the lanes are, act as our constant reference for where to steer the 
vehicle. 

This project proposes an algorithm to automatically detect lane lines using 
OpenCV and Python, including Hough Transforms and Canny edge detection. 
Detected highway lane lines on a video stream. 

#### Original video frame
![][image0]

#### Video frame with detected lane lines
![][image1]

## Code & Files
### 1. Dependencies & environment

Anaconda is used for managing my [**dependencies**](https://github.com/udacity/CarND-Term1-Starter-Kit).

* OpenCV3, Python3.5, moviepy, Jupyter Notebook
* OS: Ubuntu 16.04 (should work on other platform too)

### 2. My project files

* [P1.ipynb](P1.ipynb) is the main code for demos.

* [test_images](test_images) contains the test images.
 
* [test_videos](test_videos) contains the test videos.

Besides, there are some testing videos and images.

### 3. How to run the code

(1) If you using Anaconda or miniconda, activate your environment which includes the dependencies by:
```sh
source activate your-conda-environment
```

(2) Load _jupyter notebook_ and then select the P1.ipynb by:
```sh
jupyter notebook
```


### 4. Release History

* 0.1.0
    * The first proper release

---

## System in details

### 1. Steps
    1) apply the gaussian blur
    2) convert bgr to hsv and segment while and yellow (because it is easier in HSV space than RGB)
    3) Canny edge detection
    4) apply the designed mask to the image to obtian the region of interest
    5) apply hough transform to get lines
    6) augmented the lanes on the original image
    7) a buffer is used to smooth the line positions between frames.

### 2. Canny edge detection

Canny edge detection is implemented by using opencv function as follows:

```
edges = cv2.Canny(gray, low_threshold, high_threshold)
```
One example is shown as below:
![][image7]

### 3. Region mask

![][image2]

### 4. Hough Transform

A **line** in Image Space is a **point** in Hough Space.
![][image3]


A **point** in Image Space is a **line** in Hough Space.
**Then we divide the Hough Space into grid, and define the intersecting lines as all lines passing through a given 
grid cell.**
![][image4]


Since vertical lines have infinite slope in `y = mx+b` representation, so we define a line in polar coordinates as 
shown in the following fiugre.
![][image5]


Each **point** in image space corresponds to a **sine curve** in Hough Space. Therefore, if we take a line of points, it
translates into a whole bunch of sine curves in Hough Space, and the **intersection** of those sine curves gives the 
parameters of the line.
![][image6]


[//]: # (References)
[image0]: test_images/solidWhiteCurve.jpg
[image1]: test_images/augmented/solidWhiteCurve_augmented.jpg
[image2]: test_images/source/region_mask.jpg
[image3]: test_images/source/hough.jpg
[image4]: test_images/source/hough_line.jpg
[image5]: test_images/source/hough_polar.jpg
[image6]: test_images/source/hough_polar_1.jpg
[image7]: test_images/source/canny_example.jpg
