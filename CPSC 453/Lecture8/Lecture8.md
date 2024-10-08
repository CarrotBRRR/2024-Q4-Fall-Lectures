# Lecture 8: Oct 1
## 3D Rotation
### **Rotation Matrix**:
**Rotation about x-axis**:\
    $R_x(\theta) = \begin{bmatrix} 1 & 0 & 0 & 0\\ 0 & \cos(\theta) & -\sin(\theta) & 0\\ 0 & \sin(\theta) & \cos(\theta) & 0\\ 0 & 0 & 0 & 1 \end{bmatrix}$

**Rotation about y-axis**:\
    $R_y(\theta) = \begin{bmatrix} \cos(\theta) & 0 & \sin(\theta) & 0\\ 0 & 1 & 0 &0\\ -\sin(\theta) & 0 & \cos(\theta) & 0\\ 0 & 0 & 0 & 1 \end{bmatrix}$

**Rotation about z-axis**:\
    $R_z(\theta) = \begin{bmatrix} \cos(\theta) & -\sin(\theta) & 0 & 0\\ \sin(\theta) & \cos(\theta) & 0 & 0\\ 0 & 0 & 1 & 0\\ 0 & 0 & 0 & 1 \end{bmatrix}$

**3D Rotation about an arbitrary point**:\
    Translate to origin, rotate, translate back.\
    $R = T(-P)R_z(\theta)T(P) = $\
    $\begin{bmatrix} 1 & 0 & 0 & P_x\\ 0 & 1 & 0 & P_y\\ 0 & 0 & 1 & P_z\\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} \cos(\theta) & -\sin(\theta) & 0 & 0\\ \sin(\theta) & \cos(\theta) & 0 & 0\\ 0 & 0 & 1 & 0\\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 & -P_x\\ 0 & 1 & 0 & -P_y\\ 0 & 0 & 1 & -P_z\\ 0 & 0 & 0 & 1 \end{bmatrix}$

**3D Rotation about a given vector u**:\
    1. Align the vector with the z-axis.\
    2. Rotate about the z-axis.\
    3. Rotate back to the original orientation.\
**Example:**
    $u = \begin{bmatrix} 1/sqrt(3)\\ 1/sqrt(3)\\ 1/sqrt(3) \end{bmatrix}$\
    $\theta = 60^{\circ}$\
    \missed some stuff lol

### How to code it
First Choice: Give Coordinates of the points.\
$\begin{bmatrix} d_x \\ d_y\\ d_z \end{bmatrix}$\
Second Choice: 2 3D points\
Third Choice: 2 2D points

### Vitrual Trackball
- unprojected 2D onto the unit sphere