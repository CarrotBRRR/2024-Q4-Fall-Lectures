# Lecture 20: Nov 21
## Half Edge Data Structure
| Half Edge | Source Vertex | Face | Next | Pair |
| - | - | - | - | - |
| E_x | V1 | F1 | G_x | G_y |
| E_y | V2 | F2 | H_y | H_x |
| K_y | V3 | F2 | E_y | E_x |
| G_x | V2 | F1 | ... | ... |
| G_y | V4 | F3 | ... | ... |
| ... | ... | ... | ... |

## Vertex -> all adjacent neighbors

## Psuedo code for finding neighborhood
```c
Input v
e = V -> ege -> pair
e_0 = e
do
    w = e -> source
    // do  something with w
    e = e -> pair -> next
while e != e_0
```