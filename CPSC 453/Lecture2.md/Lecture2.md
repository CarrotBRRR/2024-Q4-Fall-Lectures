# Lecture 2: Sept 10
## Graphics Systems Cont'd...
### Common Graphic Pipeline
![Common Graphic Pipeline](<images/Screenshot 2024-09-10 140515.png>)
- Scene Data

- Application Program Interface (APIs)
    - OpenGL

- Graphics Hardware
    - Makes final raster image
    - Sends to raster display

### GPU (Graphics Processing Unit)
- Specalized processor typically found on Graphics Cards, Designed to accelerate graphics rendering and perform parallel processing tasks

![GPU Pipeline](<images/Screenshot 2024-09-10 141109.png>)

1. Vertex Shader
    -  Handles the transformation and creation of geometric primitives, such as triangles.
    - Not rasterized
2. Raseterization
    -  Converts geometric primitives into fragments, which are potential or placehodler pixels. 
    - Determines which pixel is affected by the primitive
3. Fragment Shader
    - Final colour and other attributes are determined
4. Blending
    - Combines the processed fragments to form the final pixel colours

Then Sent to Raster Display

### Frame Buffer
- To avoid flickering, the frame buffer is used to store the current frame
- Region of memory usually on the graphics card
- holds the pixel values for the current frame
- Depth of the frame buffer:
![Frame Buffer](<images/Screenshot 2024-09-10 142321.png>)

example:
![alt text](<images/Screenshot 2024-09-10 142443.png>)
Answer:

Each RGB channel is allotted 6/3 = 2 bits. These 2 bits can produce 2^2 = 4 colors in each channel. 

So, the total number of colors that can be represented is

4 ∗ 4 ∗ 4 = 64 .

The buffer size can be found by the size of screen times to the color depth. So, here we have:

8 ∗ 8 ∗ 6 = 384 bits = 48 bytes.

#### Why do we need a frame buffer?
- refreshing
- rasterization cost
- dual buffering

What is min size of frame buffer with dual buffer of display size 4500 x 3000 and color depth of 24 bits?

Answer:

4500 ∗ 3000 ∗ 24 ∗ 2 = 648000000 bits = 81000000 bytes,
or 81 MB, 77.247 MiB

### Creating left/right images in CG
- we don't need complex cameras
- put the camera anywhere


### ASS 1: serpinsky triangle
Self-Similar\
sub_triangle(A, B, C)

sub_triangle(A, D, F)\
sub_triangle(D, B, E)\
sub_triangle(F, E, C)

~~sub_triangle(D, E, F)~~

### Euclidean Dimension
- Lines, Curves: 1D
- Plane, Surface: 2D
- Cube, Volume: 3D

Rougher = higher dimension

e = magnifation factor\
N = n of self similar obj

D = log_e(N) = dimension
