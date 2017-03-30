## Project Code and its Usage
The code is available on Github: https://github.com/marthtz/CarND-Advanced-Lane-Lines-P4 

The project was cloned from the official P4 repository. I added the following files:

* In main folder (Python scripts, calibration data and this writeup)
  * cameraCal.py (script for camera calibration)
  * processPipeline.py (script to process images and videos)
  * cam_cal_pickle.p (saved transformation parameters for camera correction)
  * Writeup.pdf
* In output_images folder (processed test images and videos)
  * project_video_lane.mp4
  * challenge_video_lane.mp4
  * harder_challenge_video_lane.mp4
  * project_video_lane_debug.mp4 (plus debug info screen)
  * straight_lines1_lane.jpg & straight_lines2_lane.jpg
  * test1_lane.jpg to test6_lane.jpg
* In output_images/writeup_images folder(images mentioned in this writeup)
  * ColorSelectionTool.jpg
  * calibration1_undist.jpg
  * straight_lines1_undistorted.jpg
  * test6_original_thresholded.jpg
  * straight_lines1_original_lines.jpg
  * straight_lines1_warped_lines.jpg
  * straight_lines1_binary_warped.jpg
  * test2_left_binary_line.jpg
  * test2_binary_warped.jpg
  * video_right_binary_line.jpg
  * test2_lane.jpg
  * video_debug.jpg

### Usage of the Python scripts:
####	cameraCal.py
This scripts runs the camera calibration on the provided calibration images.

Execution is done by just calling cameraCal.py. All calibration images must be present in the subfolder ‘camera_cal’. 

The script saves the parameters used for undistorting images as ‘cam_cal_pickle.p’ in the main folder. An example of an undistorted calibration image is saved to “output_images”

####	processPipeline.py
This script runs full lane line detection on the provided images or videos. In addition, debug information can be created.

Executing is done by calling the script with input images/videos as parameter. In addition, if the first argument is ‘debug’, additional output is generated.

Examples:
* python processPipeline test_images/image1.jpg test_images/image2.jpg
* python processPipeline debug project_video.mp4 challenge_video.mp4





## Advanced Lane Finding
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


In this project, your goal is to write a software pipeline to identify the lane boundaries in a video, but the main output or product we want you to create is a detailed writeup of the project.  Check out the [writeup template](https://github.com/udacity/CarND-Advanced-Lane-Lines/blob/master/writeup_template.md) for this project and use it as a starting point for creating your own writeup.  

Creating a great writeup:
---
A great writeup should include the rubric points as well as your description of how you addressed each point.  You should include a detailed description of the code used in each step (with line-number references and code snippets where necessary), and links to other supporting documents or external references.  You should include images in your writeup to demonstrate how your code works with examples.  

All that said, please be concise!  We're not looking for you to write a book here, just a brief description of how you passed each rubric point, and references to the relevant code :). 

You're not required to use markdown for your writeup.  If you use another method please just submit a pdf of your writeup.

The Project
---

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

The images for camera calibration are stored in the folder called `camera_cal`.  The images in `test_images` are for testing your pipeline on single frames.  If you want to extract more test images from the videos, you can simply use an image writing method like `cv2.imwrite()`, i.e., you can read the video in frame by frame as usual, and for frames you want to save for later you can write to an image file.  

To help the reviewer examine your work, please save examples of the output from each stage of your pipeline in the folder called `ouput_images`, and include a description in your writeup for the project of what each image shows.    The video called `project_video.mp4` is the video your pipeline should work well on.  

The `challenge_video.mp4` video is an extra (and optional) challenge for you if you want to test your pipeline under somewhat trickier conditions.  The `harder_challenge.mp4` video is another optional challenge and is brutal!

If you're feeling ambitious (again, totally optional though), don't stop there!  We encourage you to go out and take video of your own, calibrate your camera and show us how you would implement this project from scratch!
