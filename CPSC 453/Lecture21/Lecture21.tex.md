# Lecture 21 (?)
## Phong Reflection Model
Specular Reflection: Shiny\
Diffuse Reflection: Matte\
Translucent Reflection: Glass, Water, etc.

Light source:
```math
L = \begin{bmatrix} L_r \\ L_g \\ L_b \end{bmatrix}
```
is given\
P: object, material

scalar values, component by component

I(P), reflection for each point on the triangle in the mesh\
Interpolate

we need 3 unit vectors:
l = light vector, vector from p to light source\
n = normal vector to the surface at p\
v = vector from p to the camera

### Diffuse Reflection
Same for all viewers
```math
\theta = 90\degree \rightarrow I_d = 0
```
```math
\theta = 0 \rightarrow I_d = max
```
```math
cos(\theta) = l \cdot n
```
```math
I_d \propto (l \cdot n)
```
```math
F(l, n, material, L_d)
```
```math
I_d = K_d \cdot L_d \cdot (l \cdot n)
```
L_d = Light Intensity, Diffuse Component\
Diffuse Coefficient: K_d\
Captures the material
```math
K_d = \begin{bmatrix} K_{dr} \\ K_{dg} \\ K_{db} \end{bmatrix}
```
Bright K_d = 1\
Dark K_d = 0\
#### How to determine K_d of a material?
Trial and error:\
Here are some examples
| Component | Gold | Black Plastic | Silver |
|-----------|------|---------------|--------|
| Red       | 0.75 | 0.01          | 0.5    |
| Green     | 0.6  | 0.01          | 0.5    |
| Blue      | 0.22 | 0.01          | 0.5    |

Example:
Find I_d red\
\theta = 60\degree\
material: gold\
```math
\theta = 60 \rightarrow l \cdot n = cos(60) = 0.5
```
```math
I_d^{red} = 0.75 \cdot 0.5 \cdot 1 = 0.375
```
material:
```math
1 \rightarrow 0.75 
```
angle:
```math
0.75 \rightarrow 0.375
```

### Specular Reflection
Shiny Objects\
Highlights

Point P\
Light source at theta from normal\
Reflected ray r\
reflective object\
View Angle phi from R: close to R will see the reflection better

```math
I_s \propto cos(\phi) = r \cdot v
```
```math
F(material, phi, L_s)
```
```math
I_s = K_s \cdot L_s \cdot (r \cdot v)
```
K_s = Specular Reflection Constant
```math
0 \le K_s \le 1
``` 
1 is mirror

This does not give good Highlights\
So Phong added a term to the equation
```math
I_s = K_s \cdot L_s \cdot (r \cdot v)^\alpha
```
alpha = shininess coeffiecient\
```math
1 \le \alpha \le 50
```
It "squishes" the light curve\
#### How to find r
```math
l , n \rightarrow r ?
```
```math
l + r = 2(n \cdot l)n
```
```math
r = 2(n \cdot l)n - l
```
Example
```math
l = \begin{bmatrix} -\sqrt 2 / 2 \\ \sqrt 2 / 2 \\ 0 \end{bmatrix}
```
```math
l \cdot n = \sqrt 2 / 2
```
```math
r = \sqrt 2 \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} - \begin{bmatrix} -\sqrt 2 / 2 \\ \sqrt 2 / 2 \\ 0 \end{bmatrix} = \begin{bmatrix} \sqrt 2 / 2 \\ \sqrt 2 / 2 \\ 0 \end{bmatrix}
```
### Ambient Light
```math
I_a
```
```math
I_a \propto L_a
```
```math
I_a = K_a L_a
```
```math
0 \le K_a \le 1
```
### Finally
```math
I(P) = I_a + I_d + I_s
```
### Phong Reflection Model
```math
I = K_a L_a + K_d L_d (l \cdot n) + K_s L_s (r \cdot v)^\alpha
```
```c
if(l \cdot n < 0){
    I_d = 0
}
if(r \cdot v < 0){
    I_s = 0
}
```

### Incorporating Distance
```math
d = s - p
```
```math
I(s, p) = \frac{I(p)}{d^2}
```

#### Phong
```math
I = f\frac{I(P)}{a + bd + c d^2}
```
where a, b, c are experimentally determined constants

So, the final equation is
```math
I(P) = \frac{I_a}{a + bd + c d^2} (K_a L_a + K_d L_d (l \cdot n) + K_s L_s (r \cdot v)^\alpha)
```
