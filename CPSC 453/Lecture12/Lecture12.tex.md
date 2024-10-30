# Lecture 12: Oct 17
## Stereo View
### Simple Approach:
- begin with a regular camera (Single Eye)
- Establish camera frame (U, V, N)

Left Eye:
```math
eye - du
```

Right eye:
```math
eye + du
```

### Recap
Projections:
- Parallel Projection
    - Orthographic
    - Oblique
- Perspective
- Non-Linear

## Modeling
### Curves, Surfaces, Meshes
- Parametric Models:
    - From Curves to Surfaces
    - Bezier Curves
    - B-Splines
    - NURBS: Non-Uniform Rational B-Splines (not in this course)

### Parametric Curves
```math
Q(u) = \begin{bmatrix} x(u) \\ y(u) \end{bmatrix}
```
u has a Parametric Domain 

3D Parametric Curve:
```math
Q(u) = \begin{bmatrix} x(u) \\ y(u) \\ z(u) \end{bmatrix}
```

example:
```math
Q(u) = \begin{bmatrix} cos(u) \\ sin(u) \\ u \end{bmatrix}, 0 \leq u \leq R
```
Makes a helix (or spiral)