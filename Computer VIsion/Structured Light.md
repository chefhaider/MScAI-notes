

## Overview
- **Goal**: Scanning the structure of a 3D object.
- **Focus**: Concerned with shape rather than light reflection or texture.
  
## Image Acquisition Techniques
### Passive Image Acquisition
- Takes multiple photos without any external light pattern.
- Relies on natural lighting conditions.

### Active Image Acquisition
- Involves projecting a known light pattern onto the object to assist in scanning.
- A **projector** is used to add structured light patterns that help extract 3D shape information.

## Passive vs. Active Acquisition
- **Passive**: Relies solely on camera(s) capturing the object under ambient lighting.
- **Active**: Uses additional light sources like projectors to create structured light, enhancing depth calculation. See lecture slides for detailed comparison.

## Structured Light Triangulation

### Concept
- Projects light points from a **projector** onto the object, and the **camera** captures the reflected pattern.
- Using the same triangulation principles, the position and depth of each point can be calculated.

### Speed Optimization
- Instead of projecting a single point at a time, project a whole **scan line** to speed up the process.

### Triangulation with Light Plane
- A beam of light from a projector (or laser) forms a line where it intersects the object.
- The surface of the object can be represented mathematically as a plane.
- Using triangulation, the depth of points on the object can be calculated.
  
### Laser Scanner vs. Projector
- A **laser scanner** can also be used for structured light scanning instead of a projector.
- However, this process can still be slow (e.g., taking up to 10 seconds), which is problematic when scanning moving objects like humans, where high precision is required.

## Faster Acquisition Techniques

### Multi-Strip Projection
- Instead of projecting a single line or point, project multiple stripes simultaneously for faster acquisition.

### Pattern Differentiation
- To differentiate between projected stripes, use distinct patterns. This helps in identifying the position of each stripe on the object.

#### Binary Coded Stripes
- For simple structured objects, **binary coded stripes** can be used.
- This involves projecting different patterns over time and refining the data by performing a **binary search**.
- Each pixel's position can be identified from the binary patterns it receives.

#### Color-Coded Patterns
- To make the process more efficient, use **color-coded patterns**.
- However, this adds complexity to the correspondence algorithm, especially when scanning colored objects.

### Trade-offs
- The trade-off in structured light techniques is often between:
  - **Slow but robust methods** (e.g., single point or line projection).
  - **Fast but fragile methods** (e.g., multiple stripes or color-coded patterns).
