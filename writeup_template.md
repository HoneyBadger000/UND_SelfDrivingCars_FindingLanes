# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./examples/edges.jpg "EdgeDetection"
[image3]: ./examples/roi.jpg "Region of Interest"
[image4]: ./examples/lanelines.jpg "Lanes lines"


My pipeline consisted of 5 steps. 

1. Convert the image to grayscale and apply a Gaussian blur. For the parameters, I used kernel_size = (5, 5).
![alt text][image1]
2. Apply Canny edge detection. In line with the recommended 2:1 or 3:1 ratio of thresholds, I used low_threshold = 55 and high_threshold = 165
![alt text][image2]
3. Extract the region of interest, I used a simple triangulation to extract the region of interest
![alt text][image3]
4. Hough transform to find lines , I used 
    rho = 1, theta = np.pi/180 , threshold = 20, min_line_len = 180, max_line_gap = 90	
5. Filter and process lines from hough transform.
Here, I first filtered out bad lines by rejecting slopes that indicate too horizontal or too vertical lines.
then i sorted the lines based on the largest length. I then used these sorted lines to find two lines, that have similar slope but in opposite signs
![alt text][image4]
	
### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
