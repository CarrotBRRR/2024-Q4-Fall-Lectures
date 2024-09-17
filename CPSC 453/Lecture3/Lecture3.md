# Lecture 3: Sept 12
## Fractals Cont'd...
### Von Koch Snowflake
![Von Koch Snowflake Steps](<images/Screenshot 2024-09-12 140838.png>)

![Von Koch Snowflake](<images/Screenshot 2024-09-12 141051.png>)

- infinte length

#### Let's measure the fractal dimension of the Von Koch Snowflake:

- Self Similar: N = 4
- Magnification: e = 3

D_f = log_e(N) = log_3(4) = 1.26

- Euclidean Dimension is 1

### More Examples: 
#### Menger Sponge
![Menger Sponge](<images/Screenshot 2024-09-12 141546.png>)

## Geometric Objects
#### - Points: Curves, Surfaces, Volumes, Solids
#### - Vectors: Directions, Normals, Tangents, Angles

### Transformations
- Change size or orientation of objects: 
- Instancing: Copying objects
- Expressing the Symmetry
- Viewing: Perspective, Orthographic, Projections
- Animation

### Geometric Objects
- Points, Vectors
- Vectors in 2D and 3D
- Vector Space

### Magnitude
- Length or magnitude of a vector
    - Normalized vector:\
    `||v|| = sqrt(v1^2 + v2^2 + v3^2)`

- Direction
    - Unit Vector:\
    `v / ||v||`

### Dot Product
- Dot Product or Inner Product:\

- Definition in 2D and 3D:\
`u.v = ||u|| ||v|| cos(theta)`\
`u.v = u1v1 + u2v2 + u3v3`

Also:
`cos(theta) = u.v /( ||u|| ||v|| )`

Example:\
u = [1, 0], v = [1, 1]\
u.v = 1*1 + 0*1 = 1\
||u|| = sqrt(1^2 + 0^2) = 1\
||v|| = sqrt(1^2 + 1^2) = sqrt(2)\
cos(theta) = 1/sqrt(2)
theta = 45 degrees