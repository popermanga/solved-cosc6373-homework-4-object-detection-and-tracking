Download Link: https://assignmentchef.com/product/solved-cosc6373-homework-4-object-detection-and-tracking
<br>
Object detection and tracking is a common requirement for a range of applications in computer vision.  In this assignment, we will leverage the broad understanding we have developed throughout this semester, specifically as it related to background modeling for foreground object detection, Kalman filtering for prediction of object location, and jointly, for object tracking.

This homework assignment will focus on the design of an object tracking solution that is implemented under a 2 module framework; <strong><em>a module for detection of foreground objects, and a module for tracking individual detected objects while ensuring consistent object id association using distance as a metric.</em></strong>

The overall framework can be seen in the figure below:







You are given a solution template that includes the main function that implements the overall object tracking solution as shown above.  In addition, the <strong>Track</strong> module is also available that already includes implementation of the Kalman filter that uses the centroid of detected objects as its state parameter.  The focus of this assignment will be on implementing the <strong>Detect</strong> module.  In doing so, you will also be required to implement appropriate <strong>Background Modeling</strong> approach to perform Background Subtraction and Foreground Object Detection.  Specific assignment steps are:

<ol>

 <li><strong>Background modeling (5 Pts.)</strong> – In the given BGModel() class (background_model.py), you are to implement the following background subtraction methods:

  <ol>

   <li>Background model estimated by computing the mean value of observed image intensity for each pixel</li>

   <li>Background model estimated by computing the median of observed image intensity for each pixel</li>

   <li>Background model estimated by modeling each pixel’s intensity as a Gaussian (mean and variance)</li>

   <li>Background model estimated by modeling each pixel’s intensity as a Mixture of</li>

  </ol></li>

</ol>

Gaussians (can use cv2. createBackgroundSubtractorMOG2())

<ol start="2">

 <li>Background model estimated by modeling each pixel’s intensity based on Nearest Neighbor estimate of observed intensities (can use cv2.</li>

</ol>

createBackgroundSubtractorKNN())




Note that the specific computation of the foreground image after background subtraction should be performed in the compute_fgmask() method




<ol start="2">

 <li><strong>Object detection (20 Pts.)</strong> – In the given Detectors() class (detectors.py), you are to implement approach to detect objects for tracking and their centroid values. The detector should allow for use of one of the background subtraction methods and get the foreground image.  This should be further processed to detect objects worthy of tracking.  Your choice of processing to detect objects and compute their centroids should be implemented in the Detect() method within the class. (Please note that this does not require classifier based detection of objects)</li>

</ol>




<strong><em>You should not modify the following files:                           cv_hw4.py, kalman_filter.py and tracker.py files.</em></strong>




<ol start="3">

 <li><strong>Report (5 Pts.)</strong> – Write a report outlining your approach for background subtraction and object detection.</li>

</ol>




<strong>General Instructions: </strong>

<ol>

 <li>Submit code on Github</li>

 <li>All coding must be done using <strong>python</strong></li>

 <li>Use tools available in OpenCV.</li>

 <li>Your solution needs to ensure that it executes using the following commands:</li>

</ol>

python cv_hw4.py -v QIL_orig.mp4 -b mean -d 0             python cv_hw4.py -v QIL_orig.mp4 -b median -d 0              python cv_hw4.py -v QIL_orig.mp4 -b gaussian -d 0              python cv_hw4.py -v QIL_orig.mp4 -b mog -d 0              python cv_hw4.py -v QIL_orig.mp4 -b knn -d 0

<ol start="5">

 <li>Result image will be written to the folder <em>output/</em>.</li>

</ol>

<strong> </strong>

<strong>Submission Instructions: </strong>

<ol>

 <li>Submit only the source code files.</li>

 <li>Include a readme file to describe any required set up, like location of image files that was hard coded, or any other information that is required to run the code</li>

 <li>Make sure your final submission is running on circleci. The TA will use CircleCI output and your github code for grading. TA will not be able to grade if the code does not run on circle CI.</li>

</ol>




Common reasons for failure:




<ul>

 <li>Do not use any 3rd party libraries or functions.</li>

 <li>Do not display images in your final submission. Example, cv2.imshow(), cv2.waitkey(), cv2.NamedWindow will make the circle ci fail.</li>

 <li>Do not read or write images with cv2.imread and cv2.imwrite, make sure you delete them in the final submission.</li>

 <li>Files not to be changed: requirements.txt and .circleci directory,</li>

</ul>


