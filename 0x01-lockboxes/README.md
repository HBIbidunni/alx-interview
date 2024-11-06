# Lockboxes, The ALX Project
------------

__Problem Description__
You have n number of locked boxes in front of you. 
Each box is numbered sequentially from 0 to n - 1, 
and each box may contain keys to the other boxes.

Write a Python function canUnlockAll(boxes) that determines if all the boxes can be opened.

__Prototype__

```
def canUnlockAll(boxes):
    pass
```

__Input__

`boxes`: A list of lists representing the boxes. 
Each box is represented by a list of positive integers w
here the integers represent the keys inside the box.

__Output__

Return True if all boxes can be opened, else return False.

__Constraints__

The list of `boxes` (`boxes`) will have at most length `n = 1000`.
The list of keys inside each box will have at most length `n`.
