# Lecture 5: Sept 19
## 2D Rotation
[x = [cosθ , - sinθ\
y ] = sinθ , cosθ ]

x' = x\*cosθ - y\*sinθ\
y' = x\*sinθ + y\*cosθ

### example: 90 degree rotation\
x' = x\*0 - y\*1 = -y\
y' = x\*1 + y\*0 = x

### Fixed Point
[0\
0]\
is a fixed point, because it does not change after rotation

#### Note:
$A(P) = M \cdot P$\
A is Affine

$M(\alpha_1 P_1 + \alpha_2 P_2) = \alpha_1 M(P_1) + \alpha_2 M(P_2)$

Points -> Points\
Vectors -> Vectors

Rotation is Affine

## Scaling (2D)
#### Example: Scaling by 2.5
$$\begin{bmatrix}
x'\\
y'\\
\end{bmatrix} = 
\begin{bmatrix}
2.5 & 0\\
0 & 2.5\\
\end{bmatrix}
\begin{bmatrix}
x\\
y\\
\end{bmatrix}$$

### Variations of Scaling
#### Non-uniform scaling
S is the scaling factor
$$\begin{bmatrix}
S_x & 0\\
0 & S_y\\
\end{bmatrix}$$
S_x is the scaling factor in x direction\
S_y is the scaling factor in y direction

#### Reflection
S_x = 1
S_y = -1
$$\begin{bmatrix}
1 & 0\\
0 & -1\\
\end{bmatrix}$$
This is a reflection about x-axis

#### Note:
- Scaling is Affine
- does not scale $$
\begin{bmatrix}
0\\
0\\
\end{bmatrix}$$ 

## Translation
$$P = \begin{bmatrix}
x\\
y\\
\end{bmatrix},
Q = \begin{bmatrix}
x'\\
y'\\
\end{bmatrix},
V = \begin{bmatrix}
V_1\\
V_2\\
\end{bmatrix}
$$ 
$$
x' = x + V_1\\
y' = y + V_2
$$

#### Note:
Translation is Affine