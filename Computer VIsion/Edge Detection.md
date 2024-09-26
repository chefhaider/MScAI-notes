

 - low level to high level CV tasks
 - Vanishing Point and Vanishing Line (Horizon Line)
 - How to define edges?
 - why define edges?
 -  origin of edges (kinds of discontinuity)
 - characterising edges
 - intensity function - and derivatives
 - Gaussian profile for noise and effects of noise
 - gaussian smoothing filter through convolution
 - gaussian - tradeoff between smoothing and localisation
 - **Canny Edge Detection **
	 - non max supression
	 - hysteresis thresholding (connected components) - we start extracting the strong edges and we set a threshold and thus we remove the weak edges, and then we take a lower threshold and we start seeing in edge  direciton we see if higher intensity is connected to pixel direction this removes noise
	- code 
	```python
	 - filters images with x,y derivative of Gaussian
	 - sqrt(xdx_gaussian² + ydy_gaussian² ) #find magnitude
	 - theta 0 atan2(gy,gx) # orientation of gradient
	 - Non-max supression: thin multi-pixel wide ridges to single pixel width
	 - Hysterises
		 - define to thresolds high and low
		 - use high edge to start edge curve and low threhold to continue them
		 - Follow edges, strating frmo strong edge pixels
		 - connected components
	```
