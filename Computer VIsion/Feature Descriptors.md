how to find the right scale for the interesting point?
how to model the scale?

- if we nelect scales we would get ver different feature descriptors
- if we get gaussain bigger we get smooth details and vice versa
- we can process the image with different degrees of blurring we can simulate largers scales
- for edge dection: first and second order derivatives 
- with first and second order derivatives of gaussian we can get laplacian scale - with different degrees of smoothing and getting 2nd order derivatives we can get different scales
	- we can find different local maximas and then we can detiermine the right scale be finding a max in scale direction - we find the maxomim response across the neigbouring scales across x,y, sigma
- alternate approcch - take two gaussians and subract them: which is very similar to 2nd order derivatives: the different of the gaussains give closeenuogh to do scale space search

- we want regions in the same orientation
- 