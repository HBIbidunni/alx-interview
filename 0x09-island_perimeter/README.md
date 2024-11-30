# Island Perimeter; The ALX Project
--------------
The Python function, __island_perimeter__, calculates and returns the perimeter of the island described in a given grid.
The provided script, __0-main.py__, demonstrates the usage of the island_perimeter function.

__Its Function Signature is as follows:__

```
def island_perimeter(grid):
    """Returns the perimeter of the island described in the grid.

    Args:
    - grid (List[List[int]]): A rectangular grid where 0 represents water and 1 represents land.

    Returns:
    - int: The perimeter of the island.
    """
    pass

```
> __For Instance__:

```
grid = [
    [0, 0, 0, 0, 0, 0],
    [0, 1, 0, 0, 0, 0],
    [0, 1, 0, 0, 0, 0],
    [0, 1, 1, 1, 0, 0],
    [0, 0, 0, 0, 0, 0]
]
print(island_perimeter(grid))  # Output: 12

```

__Code Explanation :briefcase::computer:__

- The __island_perimeter function__ takes a grid as input and calculates the perimeter of the island represented by the grid.
- The grid is a list of lists of integers where `0` represents water and `1` represents land.
- Each cell in the grid is square with a side length of `1`.
- Cells are connected horizontally/vertically (__not diagonally__).
- The grid is rectangular, with its width and height not exceeding `100`.
- The grid is completely surrounded by water.
- There is only one island (or nothing).
- The island doesn’t have "lakes" (water inside that isn’t connected to the water surrounding the island).
- The island_perimeter function iterates through each cell in the grid and calculates the perimeter 
based on the presence of land (`1`) and its adjacency to water (`0`). 
The algorithm checks the neighbors of each land cell and increments the perimeter accordingly.
