# Making Change; The ALX Project
------------
This project, `Making Change`, involves the creation of a Python function to determine 
the fewest number of coins needed to meet a given total amount using a given set of coins. 
The function will return the minimum number of coins required to achieve the specified total.


## Function Prototype

```
def makeChange(coins, total)

```

__Parameters__

`coins`: A list of integers representing the values of the coins in your possession.
`total`: The target total amount for which the fewest coins need to be determined.

__Return__
- The function returns the fewest number of coins needed to meet the total.
- If the total is `0` or less, the function returns `0`.
- If the total cannot be met by any combination of the given coins, the function returns `-1`.


__Example Usage__

```
from making_change import makeChange

# Example 1
print(makeChange([1, 2, 25], 37))  # Output: 7

# Example 2
print(makeChange([1256, 54, 48, 16, 102], 1453))  # Output: -1

```

__Implementation Details of the Example Usage__

`Function Logic`

- The makeChange function employs a dynamic programming approach to find the optimal solution. 
- It iteratively calculates the fewest number of coins needed for each value from `0` to the target total. 
- The function maintains an array to store these minimum values and updates them based on the available coins.

`Pseudocode`
- Initialize an array min_coins with length total `+ 1` and set all values to infinity except for min_coins[0], which is set to `0`.
- Iterate through each coin in the coins list.
- For each coin value, iterate through the min_coins array from the coin value to the target total.
- Update the minimum number of coins needed for each value.
- The final result is stored in min_coins[total]

__For instance__

```
makeChange([`1, 2, 25`], `37`)

```

Initialize min_coins as [`0, inf, inf, ..., inf`].
Iterate through each coin (`1, 2, 25`):
- `For coin 1`: Update min_coins[`1`], min_coins[`2`], ..., min_coins[`37`].
- For coin 2: Update min_coins[2], min_coins[4], ..., min_coins[36].
- For coin 25: Update min_coins[25], min_coins[26], ..., min_coins[37].
The final result is min_coins[37], which is `7`.


__Efficiency__ is crucial in this task and is required for implementation. 
The dynamic programming approach ensures that the function efficiently 
calculates the minimum number of coins for various total amounts, 
avoiding redundant computations. For future improvements, 
exploring alternative algorithms that may enhance runtime efficiency is crucial.
