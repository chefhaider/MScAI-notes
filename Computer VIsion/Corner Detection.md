Harris corner detector - fast



filter - edges - corners

detect intersting points, and describe them with feature vector
and then we can sticch the pixels togather for panorama etc
correspondances - estimate camera poses just from feature metrices i.e fundemental matrix

- on a corner in local respective field we have gradient at one direction and at another direction i.e gradient in multiple directions
- auto correlation: we get a high entensity on coreners
- [[Hessian Matrix]] - (a matrix that defines where intensities change significantly )
- classification of image points using eigen values: if we have eigen_value2>>eigen_value1 we have edge in one direction and vice versa for other direction, and if both are large values then we have corner
- Harris Corner Detector: $C = \lambda_1\lambda_2 - \alpha(\lambda_1+\lambda_2)= det(M) - \alpha trace(M)²$
	- approximates distintiveness by auto correlation
	```python
	- compute M at each pixel <- input image
	- compute image derivatives (blur first)
	- compute M components as square of derivatives
	- gaussian filter g with width sigma
	- compute C from above formula
	- threshold C to pick high values
	- non max supression

```

- invraiance:
	- **Invariance** refers to the property of a feature detection method where the detected features (e.g., corners) remain unchanged under certain transformations of the image.
	- **Covariance** refers to the property of how the detected features change in response to transformations applied to the image.
- illumination not that good, rotationan and translation is ok
- scaling: corners are not good with scaling
	- [[Feature Descriptors]]
	- 