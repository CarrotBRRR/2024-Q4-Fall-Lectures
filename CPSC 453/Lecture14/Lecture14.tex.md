# Lecture 14: Oct 24
Input for Bezeier Curves
```math
p[i] \rightarrow ControlPoints, d \rightarrow degree
```
```
for
    u = 0 to 1, q = 0; step 0.001
    q = q + Bernstein(i,d,u)*p[i]
plot
```
```math
B_{i,d}(u)=\binom{d}{i}u^i(1-u)^{d-i}
```
### example
```math
i = 2, d = 5
```
```math
B_{2,5}(u) = \binom{5}{2}u^2(1-u)^3
```
```math
= 10u^2(1-u)^3
```
save as that equation as to calculate the value of the Bezier curve at a given point.

Bottom up approach\
Dynamic Programming

### example
```math
P^2_0 = (1-u)P^1_0 + uP^1_1
```
```math
= (1-u)^2P_0 + 2u(1-u)P_1 + u^2P_2
```
```math
= Q_2(u)
```
set
```math
u=1/2
```
```math
Q_2(1/2) = 1/4P_0 + 1/2P_1 + 1/4P_2
```
de Casteljau's Algorithm\
4 points
```math
P_0, P_1, P_2, P_3
```
```math
P^1_0 = (1-u)P_0 + uP_1
```
```math
P^1_1 = (1-u)P_1 + uP_2
```
```math
P^1_2 = (1-u)P_2 + uP_3
```
```math
P^2_0 = (1-u)P^1_0 + uP^1_1
```
```math
P^2_1 = (1-u)P^1_1 + uP^1_2
```
```math
P^3_0 = (1-u)P^2_0 + uP^2_1
```
```math
Q_3(u) = P^3_0
```

Only need 2 columns
```math
P_j^{next} = (1-u)P_j^{current} + uP_{j+1}^{current}
```