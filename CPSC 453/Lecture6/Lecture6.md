# Lecture 6: Sept 24
## Affine Transformations Part 2
### Homogeneous Coordinate System
- We can use tag 1 for points and tag 0 for vectors\
eg.\
$P = \begin{bmatrix} x\\ y\\ 1 \end{bmatrix}$ is a point\
$V = \begin{bmatrix} x\\ y\\ 0 \end{bmatrix}$ is a vector\
#### Also works in 3D:
$P = \begin{bmatrix} x\\ y\\ z\\ 1 \end{bmatrix}$ is a point\
$V = \begin{bmatrix} x\\ y\\ z\\ 0 \end{bmatrix}$ is a vector

### Benefits:
$P_1 - P_2 = V$\
$\begin{bmatrix} x_1\\ y_1\\ 1 \end{bmatrix} - \begin{bmatrix} x_2\\ y_2\\ 1 \end{bmatrix} = \begin{bmatrix} x_1 - x_2\\ y_1 - y_2\\ 0 \end{bmatrix}$

$P_1 + V = P_2$\
$\begin{bmatrix} x_1\\ y_1\\ 1 \end{bmatrix} + \begin{bmatrix} x\\ y\\ 0 \end{bmatrix} = \begin{bmatrix} x_1 + x\\ y_1 + y\\ 1 \end{bmatrix}$

$V_1 + V_2 = V_3$\
$\begin{bmatrix} x_1\\ y_1\\ 0 \end{bmatrix} + \begin{bmatrix} x_2\\ y_2\\ 0 \end{bmatrix} = \begin{bmatrix} x_1 + x_2\\ y_1 + y_2\\ 0 \end{bmatrix}$

$P_1 + P_2 = P_3$\
$1/2\begin{bmatrix} x_1\\ y_1\\ 1 \end{bmatrix} + 1/2\begin{bmatrix} x_2\\ y_2\\ 1 \end{bmatrix} = \begin{bmatrix} x_1/2 + x_2/2\\ y_1/2 + y_2/2\\ 1 \end{bmatrix}$

So:
$E = \begin{bmatrix} x \\ y \\ w \end{bmatrix}$\
if $w = 0$, then $E$ is a vector\
if $w = 1$, then $E$ is a point\
else, $E$ is undefined

### 2D Affine Transformation
$A = \begin{bmatrix} a_11 & b_13 & a_13\\ a_21 & a_22 & a_23\\ 0 & 0 & 1 \end{bmatrix}$\
6 degrees of freedom

$P_1' = AP_1$
$P_2' = AP_2$
$P_m' = AP_m$

$P_1 = \begin{bmatrix} 1\\ 1\\ 1 \end{bmatrix}$\
$P_2 = \begin{bmatrix} 2\\ -1\\ 1 \end{bmatrix}$

$P_1' = \begin{bmatrix} a_11 & a_12 & a_13\\ a_21 & a_22 & a_23\\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1\\ 1\\ 1 \end{bmatrix}$ = $\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}$

so\
$a_11 + a_12 + a_13 = 2$\
$a_21 + a_22 + a_23 = -1$

#### For Determining a 2D Affine Transformation $A$, we need to know the action of $A$ on 3 points

#### For a unique solution, we need 3 points that are not collinear

### 3D Affine Transformation

$E - \begin{bmatrix} x\\ y\\ z\\ w \end{bmatrix}$\
where\
$w = 0$ for vectors\
$w$ = 1$ for points\
and ekse for undefined

#### Scaling
$\begin{bmatrix} S_x & 0 & 0 & 0\\ 0 & S_y & 0 & 0\\ 0 & 0 & S_z & 0\\ 0 & 0 & 0 & 1 \end{bmatrix}$ is a scaling matrix

#### Translation
$\begin{bmatrix} 1 & 0 & 0 & T_x\\ 0 & 1 & 0 & T_y\\ 0 & 0 & 1 & T_z\\ 0 & 0 & 0 & 1 \end{bmatrix}$ is a translation matrix

#### Rotation
$\begin{bmatrix} R_{11} & R_{12} & R_{13} & 0\\ R_{21} & R_{22} & R_{23} & 0\\ R_{31} & R_{32} & R_{33} & 0\\ 0 & 0 & 0 & 1 \end{bmatrix}$ is a rotation matrix

#### We have 12 degrees of freedom in 3D Affine Transformations

$\begin{bmatrix} a_{11} & a_{12} & a_{13} & a_{14}\\ a_{21} & a_{22} & a_{23} & a_{24}\\ a_{31} & a_{32} & a_{33} & a_{34}\\ 0 & 0 & 0 & 1 \end{bmatrix}$

$\begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{24}\\ a_{31} & a_{32} & a_{33}\end{bmatrix}$ are for Linear Transformations

$\begin{bmatrix} a_{14} \\ a_{24} \\ a_{34} \end{bmatrix}$ are for Translation

#### For a unique solution, we need 4 points that are not coplanar
