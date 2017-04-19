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


## Release History

* 0.1.0
    * The first proper release


[//]: # (References)
[image0]: test_images/solidWhiteCurve.jpg
[image1]: test_images/augmented/solidWhiteCurve_augmented.jpg

