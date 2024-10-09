# Lecture 10: Oct 8, 2024
## Projections
- Projection
    - Parallel
        - Orthographic
        - Oblique
    - Perspective

### Oblique Projection:
![Oblique Projection](<images/Screenshot 2024-10-08 142542.png>)
#### How to find the Transformation Matrix
- The projector can be specified by a 2 angles

$x_p = x + \Delta x = x + L cos(\phi) = x + z cot(\alpha)cos(\phi)$\
$y_p= y + \Delta y = y + L sin(\phi) = y + z cot(\alpha)sin(\phi)$

example:\
```math
$\begin{bmatrix} x_p \\ y_p \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & cos(\phi)cot(\alpha) & 0 \\ 0 & 1 & sin(\phi)cot(\alpha) & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix}$
```

#### Special Case: Cavalier Projection
- $\phi = 45^{\circ}$
- $cot(\phi) = 1$
    - $x_p = x + z$
    - $y_p = y + z$

#### Special Case: Cabinet Projection
- $\phi = 63.4^{\circ}$
- $cot(\phi) = 0.5$
    - $x_p = x + 0.5z$
    - $y_p = y + 0.5z$

### Quiz Example:
What is the result of applying oblique projection where $\phi = 45^{\circ}$ and $cot(\alpha) = 2$ to the point (1, 3, 3)?

#### Answer
$\begin{bmatrix} x_p \\ y_p \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 2 & 0 \\ 0 & 1 & 2 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 \\ 3 \\ 3 \\ 1 \end{bmatrix} = \begin{bmatrix} 3 \\ 5 \\ 0 \\ 1 \end{bmatrix}$

### Perspective Projection
![Derivation of Perspective Projection](<images/Screenshot 2024-10-08 144052.png>)

Example:\
$ O = (0, 0, 0)$\
$ P = (x, y, z)$\
$ P' = (x', y', z')$

$ Q = (0 , 0, z)$\
$ Q' = (0, 0, d)$

$\Delta OP'Q' = \Delta OPQ$\
because the triangles are similar and the angles are the same\

so\
$x' / x = d / z $ -> $x' = x * d / z$\
$y' / y = d / z $ -> $y' = y * d / z$

Note:
- If P is in x or y plane, then there will not be any projection for P
- Perspective is not Affine
- All points on the viewing plane are fixed points

### Extended Homogeneous Coordinate System
- Generalize homogeneous coordinate system
- Recall: the extra coordinate is used to represent "another floor"
> ex:\
$\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}$ -> $\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}$

> $\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}$ is outside the affine space

>  $\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}$ represents all points on the line from the origin to $\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}$

$W = 1:$ $\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}$\
$W = 2:$ $\begin{bmatrix} 4 \\ -2 \\ 2 \end{bmatrix}$\
$W = 3:$ $\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}$\
$W = 1/2:$ $\begin{bmatrix} 1 \\ -1/2 \\ 1/2 \end{bmatrix}$ \
So in general:
$\begin{bmatrix} 2W \\ -W \\ W \end{bmatrix}$
> Divide by W,\
aka normalization

#### Example:
$P = \begin{bmatrix} -5 \\ 10 \\ 2 \end{bmatrix}$ is given
> Outside Affine Space
> Divide by W (2 in this case) to get the point in the affine space

Representer in Affine Space: $\begin{bmatrix} -5/2 \\ 10/2 \\ 2/2 \end{bmatrix} = \begin{bmatrix} -2.5 \\ 5 \\ 1 \end{bmatrix}$

### Closed Form of Perspective Projection
$x' = x \cdot d / z$\
$y' = y \cdot d / z$\
$z' = d$

- Non-linear transformation

### 3D Extended Homogeneous Coordinate System
#### Quiz Example:
Given a 3D point, what is the point in the affine space?\
$P_o = \begin{bmatrix} 6 \\ -6 \\ 9 \\ 3 \end{bmatrix}$\
$P = \begin{bmatrix} W_x \\ W_y \\ W_z \\ 1\end{bmatrix}$

$P' = \begin{bmatrix} 3 \\ -3 \\ 4.5 \\ 1.5 \end{bmatrix}$

### Summary
$\begin{bmatrix} P \\ 1 \end{bmatrix}$ -> manipulate ->$\begin{bmatrix} Q \\ W \end{bmatrix}$ -> $\begin{bmatrix} Q/W \\ 1 \end{bmatrix}$

### NURBS
- Non-Uniform Rational B-Splines
$x_p = x d/z$\
$y_p = y d/z$\
$z_p = d$

$d/z$ -> $1/w$

$\begin{bmatrix} x \\ y \\ z \\ z/d \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 1/d & 0 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix} $ -> $\begin{bmatrix} x \cdot d/z\\ y \cdot d/z \\ z \cdot d/z \\ 1 \end{bmatrix}$ = $\begin{bmatrix} x_p \\ y_p \\ d \\ 1 \end{bmatrix}$