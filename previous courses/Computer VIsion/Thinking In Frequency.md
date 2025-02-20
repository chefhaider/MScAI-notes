
- in image we observe variations of intensity, the speed at which it varies is called frequency
### Aliasing

- aliasing is the effect if we have a frequency, sampling the frequency out of the singal: so we get a new identity from the high frequency to a lower frequency 
- how to control and predict Aliasing:
	- Nyquist Shannon Sampling Theorem:
		- when youre sampling a signal at discrete interval, the sampling frequeny should be greater then twice the max frequency of the signal i.e >= 2fmax
	- we can fix aliasing by removing the frequcies that are too high
		- Downsampling
		 ```python
		image(h,w)
		im_blur = imfilter(image, ('gaussian', 7, 1)) # remove high requency 
		im_small = im_blur(1:2:end, 1:2:end) # sample evereyother pixel 
		```

#### Fourier Series and Transform
 - A way of representing any uni-variate function in terms of  sinusoidal wave
 - Applying a Fourier Transform (FT) to an image transforms it from the spatial domain (where pixels are represented in terms of intensity and color) to the frequency domain. Here’s what you can expect from the output and how to analyze it:
	### Expectations from the Output:
	
	1. **Frequency Representation**:
	    
	    - The output image will represent different frequencies present in the original image. Low frequencies correspond to the smooth variations in intensity (like large areas of similar color), while high frequencies represent sharp transitions (like edges and noise).
	2. **Magnitude and Phase**:
	    
	    - The FT can be separated into two components:
	        - **Magnitude**: Indicates the strength of each frequency component.
	        - **Phase**: Indicates the phase shift of the frequency components, which is important for reconstructing the original image.
	3. **Visual Patterns**:
	    
	    - In the frequency domain, you may see bright spots or patterns that correspond to periodic features in the original image. For example, edges or repetitive structures will show up as distinct peaks.
 - a fourier transfrom uses complex number to store both amplitude and phase/shift
 - mgnitude is the ampilote of sign wave, and the angle determines how much it is shifted to the right
 - properties
	 - linear
	 - symmetric around origin
	 - energy of the signal is energy of the the fourier transfrom
 - see slides for before

 - ##### The convolution theorem
	 - F \[g\*h] = F\[g] F\[h] <- pointwise multiplication 
	 -
 - if preserve the the cetnre part of a fourier transform map we are preserving the low frequencies and we discard the highs, the resultant is a blurred version
 - if we preserve the high frequncies i.e discard the cetnre we get edges
 - ....
 - ....
 - Jpeg: it slices the image into n tiles (optimal for hardware computation), it then looks at individual tiles and perfroms a variant of the Fourier transform and stores the brightest contributions. with the precentage retaining we can control the quality level 
	 - it treats intensity specific from color. most jpeg images subsample chroma


## Image filtering
start with an image -> process -> get an output image

### Linear filters
- De-noising, increasing contrast analyse images by taking features, and spot recurring features
- linearly property: there are two filter operations  and then you add them back together which is identical to filtering the image only once but with a sum of two kernels i.e filter(I,f1+f2) = filter(I, f1) + filter(I, f2)
- Shift invariance: if we shift the images and then apply filter is same as applying filter before and then....
- correlation <-> convolution: its got the same effect as rotating the kernel to 180°
- convolution properties:
	- commutative: a\*b = b\*a the mathematical symbol for convolution is "\*"
	- associative: a\*(b\*c) = (a*\b)\*c - but correlation is not associatie
	- dirtibutes over addition
	- scalar factors out
	- identity: unit impulse
- Gaussian filter - example case smoothing/blurring
	- loss pass filter, blocks out high frequency in an image
- Seperability
	- A 2D filtering can be implemetned by 1d filtering followed by another... K+K instead of k^2
	- instead of implementing a 2D nested loop we implement 1D step after one another - for effiecency Its is decomposed into 1D filters
- papdding to image to incoperate filtering on edge
- Sobel Filter: Central differences to calculate slope. 

### None linear filters
....



....
....
