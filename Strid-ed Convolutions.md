

Stride refers to the number of pixels by which the filter moves (or "strides") across the input image. 

- **Stride of 1**: The filter moves one pixel at a time.
- **Stride of 2**: The filter moves two pixels at a time.
- **Stride of 3**: The filter moves three pixels at a time, and so on.

### How Strided Convolution Works

When you apply a strided convolution:

1. **Filter Movement**: Instead of moving the filter one pixel at a time (stride of 1), you move it by a larger number of pixels (the stride value). For instance, with a stride of 2, the filter moves two pixels horizontally and vertically for each step.
  
2. **Output Size**: Because the filter skips over some of the input pixels due to the stride, the output feature map is smaller than it would be with a stride of 1. This reduction in size can help reduce the computational load and capture more abstract features.

3. **Downsampling**: Strided convolution inherently performs downsampling. It reduces the spatial dimensions of the input, which can be useful for reducing the size of the feature map while retaining important features.

### Example

Suppose you have an input image of size \( 6 \times 6 \) and you use a \( 3 \times 3 \) filter with a stride of 2:

- **Input Size**: \( 6 \times 6 \)
- **Filter Size**: \( 3 \times 3 \)
- **Stride**: 2

The output feature map size would be calculated as:

$$ \text{Output Size} = \left\lfloor \frac{\text{Input Size} - \text{Filter Size}}{\text{Stride}} \right\rfloor + 1 $$

For each dimension, this becomes:

$$ \text{Output Size} = \left\lfloor \frac{6 - 3}{2} \right\rfloor + 1 = \left\lfloor \frac{3}{2} \right\rfloor + 1 = 1 + 1 = 2 $$

So the resulting feature map would be \( 2 \times 2 \) in size.

### Key Benefits

1. **Computational Efficiency**: By reducing the size of the feature map, strided convolution decreases the number of computations required in subsequent layers.
  
2. **Dimensionality Reduction**: It can help with dimensionality reduction, which can be important for reducing the complexity of the model and preventing overfitting.

3. **Feature Extraction**: Larger strides can lead to more abstract feature extraction, which might be useful in certain contexts where fine-grained details are less important.

In summary, strided convolution is a useful technique in CNNs for efficiently handling large input data and extracting higher-level features by effectively downsampling the feature maps.




**Also see Dialated convolution**
- gived wider receptive feilds with fewer paramters