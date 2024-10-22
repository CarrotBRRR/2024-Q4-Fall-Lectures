# Lecture 13: Oct 22
## Parametric Curves
- Continuous  deformation of a line segment
- u is a parameter

## Interace for creating polynomial Curves
- Formula 
- 2D (or 3D points) as Pi

### Example
Assume P0, P1, P2 are points
```math
Q(u) = P_0 + uP_1 + u^2P_2
```

```math
P_0 = \begin{bmatrix} 0 \\ 0 \end{bmatrix}, 
P_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}, 
P_2 = \begin{bmatrix} 2 \\ 0 \end{bmatrix}
```

```math
Q(0) = P_0 = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
```
```math
Q(1) = P_0 + P_1 + P_2 = \begin{bmatrix} 3 \\ 1 \end{bmatrix}
```

```math
Q(1/2) = P_0 + 1/2P_1 + 1/4P_2 = \begin{bmatrix} 1 \\ 1/2 \end{bmatrix}
```

Shift Coordinates by
```math
\begin{bmatrix} 10 \\ 0 \end{bmatrix}
```

```math
P_0^n = \begin{bmatrix} 10 \\ 0 \end{bmatrix},
P_1^n = \begin{bmatrix} 11 \\ 1 \end{bmatrix},
P_2^n = \begin{bmatrix} 12 \\ 0 \end{bmatrix}
```

```math
Q(0) = P_0^n = \begin{bmatrix} 10 \\ 0 \end{bmatrix}
```
```math
Q(1) = P_0^n + P_1^n + P_2^n = \begin{bmatrix} 55.5 \\ 1/2 \end{bmatrix}
```
```math
Q(1/2) = P_0^n + 1/2P_1^n + 1/4P_2^n = \begin{bmatrix} 11.5 \\ 1/2 \end{bmatrix}
```
Curve has been stretched

Q(u) is not Affine;
Only Q(0) is Affine

```math
{1, u, u^2, ... , u^n} 
```
is the standard basis for polynomials

```math
1 + u + u^2 = 1
```
Affine Invariant:\
sum to one

```math
B_n = u^n
```
```math
B_0(u) + B_1(u) + B_2(u) = 1
```
for every u

---
```math
(1-u) + u \equiv 1
```
```math
[(1-u) +u]^2  \equiv 1
```
```math
(1-u)^2 + 2u(1-u) + u^2 \equiv 1
```
### Quadratic Bezier Curve: (Important for Quiz)
```math
Q_2(u) = (1-u)^2P_0 + 2u(1-u)P_1 + u^2P_2
```

#### start:
```math
Q_2(0) = (1-0)^2P_0 + 2(0)(1-0)P_1 + 0^2P_2 = P_0
```
#### end:
```math
Q_2(1) = (1-1)^2P_0 + 2(1)(1-1)P_1 + 1^2P_2 = P_2
```

#### mid:
```math
Q_2(1/2) = (1-1/2)^2P_0 + 2(1/2)(1-1/2)P_1 + (1/2)^2P_2 
``` 
```math
= 1/4P_0 + 1/2P_1 + 1/4P_2
```
---
---
What about third degree?
```math
[(1-u) +u]^3  \equiv 1
```
```math
(1-u)^3 + 3u(1-u)^2 + 3u^2(1-u) + u^3 \equiv 1
```
### Cubic Bezier Curve
```math
Q_3(u) = (1-u)^3P_0 + 3u(1-u)^2P_1 + 3u^2(1-u)P_2 + u^3P_3
```

### In General
```math
Q_d(u) = B_{0,d}(u)P_0 + B_{1,d}(u)P_1 + ... + B_{d,d}(u)P_d
```
```math
Q_d(u) = \sum_{i=0}^{d} B_{i,d}(u)P_i
```
```math
B_{i,d}(u) = \binom{d}{i}u^i(1-u)^{d-i}
```

Bernstein Basis Functions in 1912
```math
[(1-u) + u]^d \equiv 1
```

### Cubic Bezier Curve Example
#### begin:
```math
Q_3(0) = (1-0)^3P_0 + 3(0)(1-0)^2P_1 + 3(0)^2(1-0)P_2 + 0^3P_3 
```
```math
= P_0
```

#### half:
```math
Q_3(1/2) = (1-1/2)^3P_0 + 3(1/2)(1-1/2)^2P_1 + 3(1/2)^2(1-1/2)P_2 + (1/2)^3P_3
```
```math
= 1/8P_0 + 3/8P_1 + 3/8P_2 + 1/8P_3
```

#### end:
```math
Q_3(1) = (1-1)^3P_0 + 3(1)(1-1)^2P_1 + 3(1)^2(1-1)P_2 + 1^3P_3
```
```math
= P_3
```

### Tangent of the Bezier Curve
```math
\lim\limits_{\Delta \to 0} Q(u + \Delta)
```
#### Example:
```math
Q_2(u) = (1-u)^2P_0 + 2u(1-u)P_1 + u^2P_2
```
```math
Q'_2(u) = -2(1-u)P_0 + 2(1-2u)P_1 + 2uP_2
```
```math
Q'_2(0) = -2P_0 + 2P_1
```
```math
Q'_2(1) = 2P_2 - 2P_1
```
### In General:
```math
Q_d(0) = P_0
```
```math
Q_d(1) = P_d
```
```math
Q'_d(0) = d(P_1 - P_0)
```
```math
Q'_d(1) = d(P_d - P_{d-1})
```