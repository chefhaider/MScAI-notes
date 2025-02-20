

## Introduction
In motion estimation, we track points that change positions in an image over time. This provides useful information about the objects in the scene:
- **Object differentiation**: Helps distinguish between different objects.
- **Object dynamics**: Provides insights into the object's movement.
- **Object shape**: Offers clues about the shape of the object.
- **Dense motion estimation**: Estimates motion for each pixel in the image, providing detailed information about movement.

## Motion Parallax
- Motion parallax refers to the phenomenon where objects at different depths appear to move at different speeds relative to the observer when in motion.
- This helps infer the relative depth of objects while the camera or the observer is moving.

## Optical Flow vs. Motion Flow
- **Optical flow**: Refers to the apparent motion of objects in a scene as perceived from the movement between successive frames in an image sequence.
  - It's based on features extracted from images.
  - The motion observed may differ from real motion due to camera angle or scene complexity (e.g., shadows, light changes).
  - **Aperture problem**: The issue where motion appears different based on the observer’s field of view, demonstrated by the "barber pole illusion"—a visual illusion where perceived motion is ambiguous.
- **Motion flow**: Represents real-world movement, which may not always be perceivable in images.

## Image Alignment
For successful image alignment, every pixel must be accounted for. The main objective is to align images (or frames) by finding the transformation that minimizes the error between them.

### Translation and Optical Flow
- In image stitching and translation, it's crucial to identify how well two images match. This can be achieved using error metrics to evaluate alignment.
  
### Error Metrics
1. **Sum of Squared Differences (SSD)**:
   - Works well for small errors, making it tolerant to low-amplitude noise.
   - However, it's sensitive to outliers and struggles with large differences.
   - Differentiable, which makes it useful for optimization.
   
2. **ESRD**:
   - Employs an L2 norm.
   - It's robust to small errors while also handling larger ones better than SSD.

### Image Overlap
- The amount of overlap between images impacts the error.
- If overlap is low, errors increase. To address this:
  - Normalize the error metric.
  - Use as much of the image as possible for more robust regularization.

### Camera Properties
- Differences between camera properties (e.g., sensor characteristics) can also introduce alignment issues.
- To account for these differences:
  - Use linear transformations to adjust the intensities of two cameras.

### Error Cross-Correlation
- Cross-correlation helps handle intensity differences between images, as the actual value scale becomes irrelevant.
- This helps compare two images even when there are lighting or intensity variations.

## Optimization for Image Alignment
Finding the right error metric and minimizing it allows for effective image translation.

- **Brute force sliding window**: This technique tries all possible alignments but is computationally expensive and doesn't scale well.
  
### Pyramid Method (Lucas-Kanade)
- A multi-resolution approach to optimization:
  - Begin by performing optimization on a lower-resolution version of the image.
  - Then gradually move to higher resolution.
  - **Advantage**: Faster convergence.
  - **Drawback**: May not guarantee finding the global minima.

### Pixel Interpolation and Jacobian
- As resolution decreases, pixel-to-pixel correspondence may no longer be exact.
- To account for this:
  - Use interpolation to estimate pixel values.
  - The **Jacobian** matrix is used to describe how much the pixel’s intensity changes as we move in the image plane.

### Iterative Optimization Steps:
```python
while not converged:
    A = jacobian(I1, u)  # Compute the Jacobian matrix
    B = residual_vector  # Compute the residual
    solve A.T * A * delta_u = A.T * B  # Solve for delta_u
    u += alpha * delta_u  # Update motion estimate (u), where alpha is the step size
    ```

### Handling Rotation

- To account for camera or object rotation:
    - Add a rotation term **R(φ)** to the error calculation.

### Non-Parallel Image Planes

- When the image planes are not parallel or the camera views are from different angles:
    - Use homography or affine transformations to align the images.