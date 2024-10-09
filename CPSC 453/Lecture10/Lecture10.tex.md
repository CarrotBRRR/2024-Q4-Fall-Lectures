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

```math
x_p = x + \Delta x = x + L cos(\phi) = x + z cot(\alpha)cos(\phi)
```

```math
y_p= y + \Delta y = y + L sin(\phi) = y + z cot(\alpha)sin(\phi)
```


example:\
```math
\begin{bmatrix} x_p \\ y_p \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & cos(\phi)cot(\alpha) & 0 \\ 0 & 1 & sin(\phi)cot(\alpha) & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix}
```

#### Special Case: Cavalier Projection
- $\phi = 45^{\circ}$
- $cot(\phi) = 1$
    - $x_p = x + z$

    - $y_p = y + z$


#### Special Case: Cabinet Projection
- $\phi = 63.4^{\circ}$

- $cot(\phi) = 0.5$

    - $
    x_p = x + 0.5z$

    - $y_p = y + 0.5z$


### Quiz Example:
What is the result of applying oblique projection where $
\phi = 45^{\circ}$
 and $
cot(\alpha) = 2$
 to the point (1, 3, 3)?

#### Answer
```math
\begin{bmatrix} x_p \\ y_p \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 2 & 0 \\ 0 & 1 & 2 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 \\ 3 \\ 3 \\ 1 \end{bmatrix} = \begin{bmatrix} 3 \\ 5 \\ 0 \\ 1 \end{bmatrix}
```


### Perspective Projection
![Derivation of Perspective Projection](<images/Screenshot 2024-10-08 144052.png>)

Example:
```math
O = (0, 0, 0)
```

```math
P = (x, y, z)
```

```math
P' = (x', y', z')
```


```math
 Q = (0 , 0, z)```
\
```math
 Q' = (0, 0, d)```


```math
\Delta OP'Q' = \Delta OPQ```
\
because the triangles are similar and the angles are the same\

so\
```math
x' / x = d / z ```
 -> ```math
x' = x * d / z```
\
```math
y' / y = d / z ```
 -> ```math
y' = y * d / z```


Note:
- If P is in x or y plane, then there will not be any projection for P
- Perspective is not Affine
- All points on the viewing plane are fixed points

### Extended Homogeneous Coordinate System
- Generalize homogeneous coordinate system
- Recall: the extra coordinate is used to represent "another floor"
> ex:\
```math
\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}
```
```math
\downarrow
```
```math
\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}
```


> ```math
\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}```
 is outside the affine space

```math
\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}
```
represents all points on the line from the origin to 
```math
\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}
```


```math
W = 1:```math
 ```math
\begin{bmatrix} 2 \\ -1 \\ 1 \end{bmatrix}```
\
```math
W = 2:```math
 ```math
\begin{bmatrix} 4 \\ -2 \\ 2 \end{bmatrix}```
\
```math
W = 3:```math
 ```math
\begin{bmatrix} 6 \\ -3 \\ 3 \end{bmatrix}```
\
```math
W = 1/2:```math
```math
\begin{bmatrix} 1 \\ -1/2 \\ 1/2 \end{bmatrix}
```

So in general:
```math
\begin{bmatrix} 2W \\ -W \\ W \end{bmatrix}
```

- Divide by W,\
aka normalization

#### Example:
```math
P = \begin{bmatrix} -5 \\ 10 \\ 2 \end{bmatrix}
```
is given
> Outside Affine Space
> Divide by W (2 in this case) to get the point in the affine space

Representer in Affine Space: 
```math
\begin{bmatrix} -5/2 \\ 10/2 \\ 2/2 \end{bmatrix} = \begin{bmatrix} -2.5 \\ 5 \\ 1 \end{bmatrix}
```

### Closed Form of Perspective Projection
```math
x' = x \cdot d / z
```

```math
y' = y \cdot d / z
```

```math
z' = d
```

- Non-linear transformation

### 3D Extended Homogeneous Coordinate System
#### Quiz Example:
Given a 3D point, what is the point in the affine space?\
```math
P_o = \begin{bmatrix} 6 \\ -6 \\ 9 \\ 3 \end{bmatrix}
```

```math
P = \begin{bmatrix} W_x \\ W_y \\ W_z \\ 1\end{bmatrix}
```

```math
P' = \begin{bmatrix} 3 \\ -3 \\ 4.5 \\ 1.5 \end{bmatrix}
```


### Summary
```math
\begin{bmatrix} P \\ 1 \end{bmatrix}
```

```math
\downarrow
```
```math
manipulate
```
```math
\downarrow
```
```math
\begin{bmatrix} Q \\ W \end{bmatrix}
```
```math
\downarrow
```

```math
\begin{bmatrix} Q/W \\ 1 \end{bmatrix}
```


### NURBS
- Non-Uniform Rational B-Splines
```math
x_p = x d/z
```

```math
y_p = y d/z
```

```math
z_p = d
```
##

```math
d/z
```
```math
\downarrow
``` 
```math
1/w
```
# 

```math
\begin{bmatrix} x \\ y \\ z \\ z/d \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 1/d & 0 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix}
```
```math
\downarrow
```
```math
\begin{bmatrix} x \cdot d/z\\ y \cdot d/z \\ z \cdot d/z \\ 1 \end{bmatrix}
=
\begin{bmatrix} x_p \\ y_p \\ d \\ 1 \end{bmatrix}
```
