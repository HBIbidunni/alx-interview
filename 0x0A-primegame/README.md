# Prime Game: The ALX Project
----------------
This project focuses on implementing a __prime numbers game__. 
The goal is to create a __Python program__ that allows __two players__ (`Maria` and `Ben` in this case) 
to engage in a game where they take turns choosing __prime numbers__ from a set of __consecutive integers__ 
starting from `1` up to and including `n`. 

The selected __prime number__ and __its multiples__ are then removed from the set. 
The player who cannot make a move loses the game. The objective is to determine, assuming 
`Maria` always goes first and both players play optimally, who the winner of each game is.
__Both players__ take turns and __choose prime numbers to accumulate points__. 
The game continues until there are __no more prime numbers left__.

__Function Prototype__

```
def isWinner(x, nums):
    """
    Determine the winner of each game played.

    Args:
    - x (int): Number of rounds
    - nums (list): Array of integers representing 'n' for each round

    Returns:
    - str: Name of the player that won the most rounds
    - None: If the winner cannot be determined
    """
    pass

```

The prototype constraints include the following:
- `x`and `n` will not be larger than `10000`.
- No external packages can be imported.

__Game Rules__
- The game starts with a list of prime numbers.
- Two players take turns choosing a prime number from the list.
- The chosen prime number is removed from the list, and the player earns points equal to the chosen prime.
- The game continues until there are no more prime numbers left.
- The player with the highest score at the end wins.


## THE MAIN GAME

```
x = 3
nums = [4, 5, 1]

# First round: 4
# Maria picks 2 and removes 2, 4, leaving 1, 3
# Ben picks 3 and removes 3, leaving 1
# Ben wins because there are no prime numbers left for Maria to choose

# Second round: 5
# Maria picks 2 and removes 2, 4, leaving 1, 3, 5
# Ben picks 3 and removes 3, leaving 1, 5
# Maria picks 5 and removes 5, leaving 1
# Maria wins because there are no prime numbers left for Ben to choose

# Third round: 1
# Ben wins because there are no prime numbers for Maria to choose

# Result: Ben has the most wins

```

__Here's a step-by-step breakdown of the implementation of the main game__:

`Prime Number Checker`
- A helper function is needed to check if a given number is prime. It can be implemented as a simple function using:

```
def is_prime(num):
    """
    Check if a given number is prime.

    Args:
    - num (int): The number to check for primality.

    Returns:
    - bool: True if the number is prime, False otherwise.
    """
    if num < 2:
        return False
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            return False
    return True

```

`Game Logic`
- The main game logic is implemented within the `isWinner` function:

```
def isWinner(x, nums):
    """
    Determine the winner of each game played.

    Args:
    - x (int): Number of rounds
    - nums (list): Array of integers representing 'n' for each round

    Returns:
    - str: Name of the player that won the most rounds
    - None: If the winner cannot be determined
    """
    maria_wins = 0
    ben_wins = 0

    for i in range(x):
        n = nums[i]
        current_player = "Maria" if i % 2 == 0 else "Ben"
        moves_left = True

        while moves_left:
            # Find the largest prime number less than or equal to n
            chosen_prime = max(p for p in range(2, n + 1) if is_prime(p))

            # Remove chosen_prime and its multiples from the set
            n -= chosen_prime
            if n <= 0 or not any(is_prime(p) for p in range(2, n + 1)):
                moves_left = False

        # Update the winner count
        if current_player == "Maria":
            ben_wins += 1
        else:
            maria_wins += 1

    # Determine the overall winner
    if maria_wins > ben_wins:
        return "Maria"
    elif ben_wins > maria_wins:
        return "Ben"
    else:
        return None

```

`Testing`
- The next step is to test the implementation using:

```
x = 3
nums = [4, 5, 1]
result = isWinner(x, nums)
print(f"Result: {result} has the most wins.")

```

The output is:

```
Result: Ben has the most wins.

```


