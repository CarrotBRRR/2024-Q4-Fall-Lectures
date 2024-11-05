# Lecture 17: Nov 5
## Bezier Surface
```math
\sum_{i=0}^{n} \sum_{j=0}^{m} P_{i,j} B_{i,n}(u) B_{j,m}(v) 
```

## Cubic Bezier Patch
```math
d = d' = 3
```

```math
\sum_{i=0}^{3} \sum_{j=0}^{3} P_{i,j} B_{i,3}(u) B_{j,3}(v) 
```
- 4*4 terms
- 16 control points
```math
Q(0,0) = P_{0,0}
```
```math
Q(0,1) = P_{0,3}
```
```math
Q(1,0) = P_{3,0}
```
```math
Q(1,1) = P_{3,3}
```

### How to render a Bezier Patch?
- Trust deCasteljau lmao
```matlab
input P_{i,j}, d, d'
output Q(u,v)

r = 0
for u = 0 to 1 step 0.01
    s = 0
    for v = 0 to 1 step 0.01
        Q(u,v) = 0
        for i = 0 to d
            R_i = deCasteljau(P_{i,[0,...,d]}, v)
        end
        for j = 0 to d'
            q_{r,s} = deCasteljau(R_{[0,...,d]}, u)
            s++
        end
    end
    r++
end
```

### B-Spline Subdivision
- B-Spline Curves are created using subdivision methods
### Subdivision as a modeling paradigm
- Use curve schemes:
    - network of control points

### Curves:
- Open Curves
- Closed Curves

### Topologies:
- Open - Open:      Open u Open v
- Closed - Open:    Open u Closed v
- Closed - Closed:  Closed u Closed v

## Tensor Product Surfaces
## Polygonal Mesh
- General Topology
- Sequence of faces
    - Each face is a sequence of vertices
- vertex : [x,y,z]
- Edges

### Tetrahedron
- Use right hand rule to determine the normal of the face
```math
F_1, F_2, F_3, F_4
```
```math
F1 = [v_1, v_2, v_3]
```
```math
F2 = [v_1, v_3, v_4]
```
```math
F3 = [v_1, v_4, v_2]
```
```math
F4 = [v_2, v_3, v_4]
```
```math
V_1 = [1, 1, 1]
```
```math
V_2 = [2, 0, 0]
```

#### How to find the normal of a face?
