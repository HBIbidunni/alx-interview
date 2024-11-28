# Rotate 2D Matrix - The ALX Project
--------------
The script, __rotate_2d_matrix.py__, implements a function 
to rotate a 2D matrix `90°` clockwise. The rotation is performed 
in-place, indicating that the original matrix is modified 
without using additional space.

## File Overview

`rotate_2d_matrix.py`: 
- Defines a function to rotate a given 2D matrix 90° clockwise in place.

`rotate_2d_matrix(matrix)`:
- This is the main function and it rotates the input matrix in place.
- The matrix is modified directly and does not return anything.

__Function Documentation__
`rotate_2d_matrix(matrix)`:
- Rotates a square 2D matrix 90° clockwise.

`Parameters`
- matrix (list of lists): A square 2D matrix where each inner list 
represents a row of the matrix. The matrix should be of size `n x n` 
(same number of rows and columns).

- The above matrix returns nothing and is updated in place.

`Algorithm Details`
- Two pointers, `left and right`, are used to define the boundaries 
of the current layer being processed.

- Starting from the outermost elements of each layer are rotated 
in a circular manner.

- The operation is repeated for inner layers until the pointers meet.

`Usuage Instructions`
- Import the `rotate_2d_matrix` function into the project or 
run the script directly to test the rotation.

For instance:

```
from rotate_2d_matrix import rotate_2d_matrix

# Define a sample 2D matrix
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print("Original Matrix:")
for row in matrix:
    print(row)

# Rotate the matrix
rotate_2d_matrix(matrix)

print("\nRotated Matrix:")
for row in matrix:
    print(row)

```

__The resulting output is__:

```
Original Matrix:
[1, 2, 3]
[4, 5, 6]
[7, 8, 9]

Rotated Matrix:
[7, 4, 1]
[8, 5, 2]
[9, 6, 3]

```


