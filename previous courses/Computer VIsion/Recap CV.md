
## [[Thinking In Frequency]]
Aliasing
nyquist shannon thoerem
downsampling
fourier transform
	magnitude, phase shift
	properties
convolution theorem
low and high pass filtering
deconvoluiton
jpeg - algorithim

### [[Edge Detection]]
vanishing point and line
purpose
factors of edges
characterising edges - intensity function - derivative
effects of noise
gaussian smoothing and effects
derivative theorem of convolution
designing edge detection
canny edge detector - algorithim


### [[Corner Detection]]
use case
characteristics of good features
**corner detection by auto correlation**
Hessian matrix for corner detection
Interpreting the second moment matrix/ eigen values
**Harris corner detection**
properties of Harris Corner Detection
harris corner detection - algorithim
invariance and covariance
effects of transformation

### [[Feature Descriptors]]

scaling with derivatives of gaussian
scaling with subracting gaussian
SIFT algorithim?
SURF algorithim?
Nearest Neighbour Ratio?

### [[Camera Optics]]

## [[SVD]]

### [[Camera Calibration]]
common transformations - 6
properties of affine
projective transformation and homogeneous space
**camera (projection) matrix**
calibrating camera finding M (intrinsic and excentic)
	**least Square Regression problem**
	problem
	**total leas square**
	pros and cons to least square
**calibrating the camera with known geometry**
	**methode1**
	**methode2**
pros and cons of linear methode
**RQ factorisation**


### [[Epipolar Geometry]]



### [[Dense Motion Estimation]]
introduction
motion parrallax
optical flow vs motion flow
	aperture problem
image alignment
translation and optical flow
**Error Metrics** and charachteristics
	SSD
	SAD
	L_p
	SRD
	WSRD
	Bias and Gain
	Cross Corelation
	
Estimation of translation and  Optimisation
	Brute
	Pyramid method
	**Jakobian matrix**
	opitmisaiton algorithim - algorithim 
	**Handling Rotation / Parametric Motion** - 8 degrees of freedom
	Lukas-Kanade with paramtric motion
patch based optical flow
regularization based optical flow
flow-net
flow-net 2.0


### [[Stereo Vision]]
Multi-view geometry problems
	structure
	motion
	optical flow
	stereo correspondences
binocular stereo
correspondace and recosntruction
disparity
**Triangulation**
impact of baseline small vs large
vergance
stereo image rectification
Point Correspondence
correlation based window matching