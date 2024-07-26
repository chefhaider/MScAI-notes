

 - using receptive field for every neuron that is like a filter kernel
 - compute the same weights over the entire image essentially convolution and produce different feature maps
 - the feature map goes into a pooling layer which brings abstraction and magnification  of the image 
 - repeat the process until there are abstract representations which is fed into fully connected layers
 -  which maps to the final classes for classification
*last layer of fully connected layers can be replaced with channel direction layer of 1x1 convolution, by using global average pooling we can also use input image of arbitrary size*
## [[Convolution]]

convolution can be defined as integral of two functions where you shift one function over the other

exploit the spacial structure by only connecting pixels in the neighbourhood - constructing networks that have trainable filter masks

- **Local Connectivity: Convolutional layers exploit the spatial structure of data. Instead of connecting every neuron in one layer to every neuron in the next layer (like in fully connected layers), convolutional layers connect each neuron to only a local region of the input volume, often referred to as the receptive field. This means each neuron is responsible for only a small region of the input.**
- fourier transformation can also be used for convultion alternative


convolution can be expressed in terms of matrix multiplication and same formula as fully connected layers can be used

$$
\Delta w = E^T W
$$


#### Convolution Equation for Integration of Two Functions

The convolution of two functions f(t) and g(t) is defined by the integral:

$$(f∗g)(x)=\int_{-\inf}^{\inf}f(x)g(x-\tau) d\tau$$


Convolution essentially "slides" one function over another and integrates the product of the two functions at each position. This operation combines the two functions into a new function that represents how one function modifies or smears out the other.

#### Relationship to Cross-Correlation

in cross correlation we move in a negative directions, where as for convolution we move in a positive direction

$$(f⋆g)(t)=\int_{-\inf}^{\inf}f(τ)g(τ+t) dτ$$

In this definition, f(τ) is correlated with g(τ+t), which involves a shift by t rather than −t as in convolution. Essentially, cross-correlation measures the similarity between f and g as a function of the lag t.

---


- [[Padding]]
- [[Strid-ed Convolutions]]

- 1x1 convolution, can act as a flatten layer, as it essentially compresses all the channels
	- helps reduce redudancy in feature space
- [[Pooling]] - reduce dimenstionality across the feature spaxe
	*see slides*
	
	with strided convolution you may not need to encode max pooling as an addiotnal step. implements pooling and conv at the same time
- 




---
### [[Inception Model]]
fix the step of having to convolution and pooling in alteration
combining different neighbourhoods, pooling, etc

try different kernels and pooling and then concatenate the filters - by performing these operatoins in parellel then the  next layer can see which input to trust the most inorder to consrtuct the deep network

we can also add, 1x1 filter before each filter to in the parallel layer to reduce dimensions