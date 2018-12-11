## Advanced Lane Finding

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.




### Compute the camera calibration matrix and distortion coefficients given a set of chessboard images

Camera calibration matrix and distortion coefficients are computed using the chasebaord images provided in the project. And this informations are used to first undistored other images and then perpecive transrom the undistorted images. The images below are undistorted images on one of the chesboard images.

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/undist1.chess.png)



All list of undistorted chessboard images are given the jupyter notebook above (https://github.com/kulu80/Advanced_LaneDetection/blob/master/Advanced_Lane_Detection_P2.ipynb)


In addistion to applying undistort for chessboard images, undistortion is also applied for the raw images provided in the project. Below is undistored raw image.

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/undist_reall.png)


###  Use color transforms, gradients, etc., to create a thresholded binary image.
I have applied different kinds of transromation on the raw images, the python code or function used and more transforms can be found on the main jupyter notebook (https://github.com/kulu80/Advanced_LaneDetection/blob/master/Advanced_Lane_Detection_P2.ipynb)

#### Sobel y transform 

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/theshold_soble_y.png)

#### Sobel X transform 
![alt text ](https://github.com/kulu80/Advanced_LaneDetection/blob/master/sobel-x_trans.png)

### Magnitude thresholding
![atl text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/threshold_maginitue.png)

### Direction thresholding

![atl text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/theshold_dir.png)

### Color thresholding 
![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/hls_threshold_R.png)

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/hls_threshold_B.png)

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/hls_threshold_G.png)

### HLS thresholding

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/hls_real_threshold_S.png)


### Combined thresholding

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/combined_hlsand_soblex.png)


### Apply a perspective transform to rectify binary image ("birds-eye view")

Perspective transform is performed on undistorted binary images. The follwoing is one example. Full list of images and scripts are included in the juoyter notebook attached above. 

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/combined_hls_soblex%2Bpersp.png)
 **perspective transform applied on combined thresholded binary image**
 
 ### Detect lane pixels and fit to find the lane boundary
 
 Lane pixel detection is perfromed using sliding window and with out using sliding winds by seaching around pixels already found or detecting using sliding winds (please the jupyter note book for detail). After the lane pixels have been identified a polynomial fit is apply on the detected pixels. The following images are the results of this processes. 
 
 #### Sliding windows and fit polynomial
 ![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/slidingandpolyfit.png)
 
 #### Search pixel around detected pixel and fit ploynomial 
 ![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/withoutsliding%20and%20ployfit.png)
 
###  Lane curvature and warp detected lane boundaries to the original image 
 Finally the curvature of the lane and vehicle position with respect to center is determined. And warp the detected lane boundaries back onto the original image with lane boundaries and lane curvature and vehicle position displayed. 

![alt text](https://github.com/kulu80/Advanced_LaneDetection/blob/master/drawback_to_realimage.png)
