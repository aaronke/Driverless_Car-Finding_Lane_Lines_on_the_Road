# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

* This project is one of the course projects in Udacity driverless car nanodegree term1.
  Goal of this project is to find the driving lanes of road video.

---

### 1. Project pipeline


My pipeline consisted of 5 steps:
* Convert the images into grayscale.
* Using Canny edge detection to identify edges including lanes
* Hough transform is used to filter out driving lanes
* Then we have a customized draw_lines function to draw two single lines on the images.
* Finanly process the image frame of the video one by one, then create a new video with drawing lines.


In order to draw a single line on the left and right lanes, draw_lines() function is modified.

All the lines found by hough transform method are classified into left/right group by slope.
Then linregress mothed used to fit a line to get slope, intercept so that we can calculate the top/bottom points
of the left/right lanes.

![alt text](./test_videos_output/car_lane_video_right_.gif)


### 2. Potential shortcomings with current pipeline

* Noticed in a few image frames, no lane is identified makes the video drawing red lane flashing.
* A more precise method is needed to skip the detected lane which are not possible to be a driving lane.


### 3. Suggest possible improvements to current pipeline

* Provide a robust method for interset_area as the lane position will be changed depend on driving condition.
* Curve roads need to be considered.
