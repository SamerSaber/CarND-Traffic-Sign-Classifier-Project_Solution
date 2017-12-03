#**Traffic Sign Recognition** 


[//]: # (Image References)

[image1]: ./examples/visualization.jpg "Visualization"
[image2]: ./examples/grayscale.jpg "Grayscaling"
[image3]: ./examples/random_noise.jpg "Random Noise"
[image4]: ./examples/placeholder.png "Traffic Sign 1"
[image5]: ./examples/placeholder.png "Traffic Sign 2"
[image6]: ./examples/placeholder.png "Traffic Sign 3"
[image7]: ./examples/placeholder.png "Traffic Sign 4"
[image8]: ./examples/placeholder.png "Traffic Sign 5"

## Rubric Points

---
###Writeup / README


####1. Provide a basic summary of the data set. In the code, the analysis should be done using python, numpy and/or pandas methods rather than hardcoding results manually.

I used the pandas library to calculate summary statistics of the traffic
signs data set:

* The size of training set is 34799
* The size of the validation set is 4410
* The size of test set is 12630
* The shape of a traffic sign image is (32, 32, 3) 
* The number of unique classes/labels in the data set is 43


###Design and Test a Model Architecture

####1. Preprocessing

* First step convert to gray scale image.
* Then gray scale image normalization


####2. Describe what your final model architecture looks like including model type, layers, layer sizes, connectivity, etc.) Consider including a diagram and/or table describing the final model.

My final model consisted of the following layers:

| Layer         		|     Description	        					| 
|:---------------------:|:---------------------------------------------:| 
| Input         		| 32x32x1 RGB image   							| 
| Convolution 3x3     	| 1x1 stride, Valid padding, outputs 28x28x6 	|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 14x14x6 				|
| Convolution 3x3	    | 1x1 stride, Valid padding, outputs 10x10x96 	|
| RELU					|												|
| Max pooling	      	| 2x2 stride,  outputs 5x5x16 				|
| Fully connected		| Input = 400. Output = 120 	|
| RELU					|												|
| Dropout					|											|
| Fully connected		| Input = 120. Output = 84 	|
| RELU					|												|
| Dropout					|											|
| Fully connected		| Input = 84. Output = 43 	|
|						|												|
|						|												|
 


####3. Training model

* AdamOptimizer with rate = 0.0005
* EPOCHS = 50
* BATCH_SIZE = 150


####4. Output Description

My final model results were:

* training set accuracy of 0.998
* validation set accuracy of 0.962 
* test set accuracy of 0.939


###Test a Model on New Images

####1. German traffic signs found on the web.

Here are five German traffic signs that I found on the web:
[image4]: ./webImages/459381023.jpg "Traffic Sign 1"
[image5]: ./webImages/459381091.jpg "Traffic Sign 2"
[image6]: ./webImages/459381273.jpg "Traffic Sign 3"
[image7]: ./webImages/467030179.jpg "Traffic Sign 4"
[image8]: ./webImages/stock-photo-german-traffic-sign-prohibiting-thoroughfare-of-lorries-vehicles-with-a-gross-weight-over-249176164.jpg "Traffic Sign 5"


![alt text][image4]
![alt text][image5]
![alt text][image6] 
![alt text][image7] 
![alt text][image8]


I found difficulties to have images with the same size on the web, so I had to resize this images using opencv which causes alot of damage to the images.

####2. Discuss the model's predictions on these new traffic signs and compare the results to predicting on the test set. At a minimum, discuss what the predictions were, the accuracy on these new predictions, and compare the accuracy to the accuracy on the test set (OPTIONAL: Discuss the results in more detail as described in the "Stand Out Suggestions" part of the rubric).

Here are the results of the prediction:

| Image			        |     Prediction	        					| 
|:---------------------:|:---------------------------------------------:| 
| Speed limit (30km/h)      	| Speed limit (30km/h)   									| 
| Speed limit (60km/h)     	| No entry 										|
| stop				| Road work										|
| turn right ahead	      	| Priority road					 				|
| Vehicles over 3.5 metric tons prohibited			| Vehicles over 3.5 metric tons prohibited      							|


The model was able to correctly guess 2 of the 5 traffic signs, which gives an accuracy of 40%.


