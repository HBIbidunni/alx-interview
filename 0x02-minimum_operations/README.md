# Minimum Operations; The ALX Project
-------------

In this project, the task is to solve a problem that involves 
finding the minimum number of operations required to achieve a specific target 
using two basic operations: __copy__ and __paste__. The goal is to develop 
a function that computes the minimum steps required to reach the desired 
number of characters, given these constraints.

## Problem Statement
Starting with a single character `H`, only two operations can be performed:

- `Copy All`: Copy all characters currently in the editor.
- `Paste`: Paste the copied characters at the end of the existing ones.
Given a target integer `n`, the objective is to find the minimum number of 
operations required to have exactly `n` characters of `H` in the file.

## Requirements

- __Python 3__ is required to run this code.
- The code should follow the __PEP 8__ coding style.
- All functions and methods must include docstrings explaining their functionality.

## Solution Strategy
The goal is to solve the __problem statement__ by reaching exactly `n` characters 
using the minimum number of operations. This could be solved using factorization. 
The main insight is that each time `n` is divided by a smaller factor, 
`Copy All` and `Paste` operations are applied effectively to minimize steps 
indicating that if `n` is brokendown into prime factors, the minimum number of 
operations would be the sum of these prime factors.

__Steps in the Algorithm__

- `Prime Factorization`: Breakdown the target number `n` into its prime factors.
For each  __factor f__, add it to the count of operations as it represents the 
necessary steps (__copying and pasting__) to reach a size divisible by `f`.

- `Sum of Factors`: Once the factors have been identified, sum them up to get 
the minimum number of steps. For instance:

```
- For `n = 9`:
Decompose 9 into 3 * 3, to get 3 + 3 = 6 operations.

- For `n = 18`:
Decompose 18 into 2 * 3 * 3, to get 2 + 3 + 3 = 8 operations.

```

__Function Prototype__
The main function, `minOperations`, should have the following prototype:

```
def minOperations(n: int) -> int:

```

- __Parameters__: `n` (an integer representing the target number of `H` characters).
- __Returns__: Minimum number of operations to reach exactly `n` characters.
If `n` is impossible to reach (e.g., `n < 2`), the function should __return 0__.

__Usage__
An example of usuage is presented below:

```
# Import the function
from 0x02-minimum_operations import minOperations

# Example
n = 9
print(minOperations(n))  # The Output is 6

n = 18
print(minOperations(n))  # The Output is 8

```
__Explanation__
For `n = 18`, the operations sequence would follow:

Copy all (`1 operation`), Paste 2 (`total 2 characters`).
Paste (`4 characters`), Paste (`6 characters`), Paste (`12 characters`).

