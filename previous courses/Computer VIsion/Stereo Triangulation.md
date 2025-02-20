 
Stereo triangulation in computer vision is used to estimate the 3D position of a point in space from two or more 2D images taken from different viewpoints (typically from two cameras, hence "stereo"). The core idea is to find corresponding points in the images and use the known camera positions and orientations to reconstruct the 3D point through geometric triangulation.

### Purpose of Stereo Triangulation:
- **Depth Estimation**: To calculate the depth (or distance) of an object or feature relative to the cameras.
- **3D Scene Reconstruction**: Used to create 3D models or maps from 2D images, useful in applications like autonomous driving, robotics, AR/VR, and object recognition.

### Key Concepts:

1. **Epipolar Geometry**: Relates the 3D point to its projections on the two image planes. The **epipolar line** in one image defines where a point corresponding to a point in the other image must lie.
2. **Corresponding Points**: A point in 3D space appears at different positions in two images. These are called corresponding points.

### Steps to Perform Stereo Triangulation:

#### 1. **Capture Two Images from Different Viewpoints:**
   - Ensure the cameras are calibrated (i.e., their intrinsic and extrinsic parameters are known). Calibration helps relate the pixel positions in the images to real-world coordinates.
   - Define the baseline, the distance between the two cameras.

#### 2. **Find Corresponding Points in the Two Images:**
   - Use algorithms (e.g., SIFT, SURF, or matching based on color and texture) to detect the same feature in both images. These points must lie on corresponding epipolar lines.

#### 3. **Measure Disparity:**
   - The disparity is the horizontal difference in the pixel positions of corresponding points in the two images. 
   - For a point \((x_L, y_L)\) in the left image and \((x_R, y_R)\) in the right image, disparity \(d\) is:
     $$
     d = x_L - x_R
     $$
   - This disparity is directly related to depth.

#### 4. **Apply the Stereo Triangulation Formula:**
   - Assume we know the camera matrices \(P_L\) and \(P_R\) for the left and right cameras. Each projection matrix is derived from the camera calibration parameters.
   - The relation between a 3D point \((X, Y, Z)\) and its image point \((x, y)\) can be written using the **pinhole camera model**:
     $$
     s \begin{bmatrix} x \\ y \\ 1 \end{bmatrix} = P \begin{bmatrix} X \\ Y \\ Z \\ 1 \end{bmatrix}
     $$
     where \(s\) is a scale factor and \(P\) is the projection matrix.

#### 5. **Use Geometry to Find Depth \(Z\):**
   - The depth (Z) of a 3D point is related to the disparity \(d\), the baseline \(B\) (distance between the cameras), and the focal length \(f\) of the camera:
     $$
     Z = \frac{f \cdot B}{d}
     $$
   - As disparity decreases, the distance (depth) increases, and vice versa.

#### 6. **Compute the 3D Coordinates:**
   - Once you know the depth \(Z\), you can back-project to find the 3D coordinates \((X, Y, Z)\) of the point using:
     $$
     X = \frac{x_L \cdot Z}{f}, \quad Y = \frac{y_L \cdot Z}{f}
     $$

### Example in Mathematical Terms:
Suppose:
- The cameras are aligned horizontally, so we only consider \(x\) coordinates (for simplicity).
- We have a left image point \((x_L, y_L)\) and a right image point \((x_R, y_R)\).

#### Step-by-step:
1. **Measure disparity**: \(d = x_L - x_R\).
2. **Use baseline \(B\), focal length \(f\)**, and disparity \(d\) to compute depth \(Z\):
   $$
   Z = \frac{f \cdot B}{d}
   $$
3. **Compute 3D coordinates**:
   $$
   X = \frac{x_L \cdot Z}{f}, \quad Y = \frac{y_L \cdot Z}{f}
   $$

This allows you to estimate the 3D position of any point in the scene, based on two 2D images.