# The ALX Project - UTF-8 Validation
-----------
This project focuses on implementing a method to validate whether 
a given data set represents a __valid UTF-8 encoding__. 
The objective is to create a function named `validUTF8(data)` 
that takes a list of integers as input, where each integer represents __1 byte of data__. 
The function will determine if the input data set adheres to the __UTF-8 encoding rules__. 
If the data set is a __valid UTF-8 encoding__, the function will return `True`; otherwise, it will return `False`.


## Function Prototype

```
def validUTF8(data):
    """
    Determines if a given data set represents a valid UTF-8 encoding.
    
    Args:
        data (List[int]): List of integers representing 1 byte of data each.
        
    Returns:
        bool: True if data is a valid UTF-8 encoding, else False.
    """
    # Implementation of the validation logic goes here
```

__UTF-8 Encoding Rules__

`Character Length`: Characters can be __1 to 4 bytes__ long in `UTF-8`. For instance,

__In UTF-8__:

- Characters within the __ASCII range__ (`0 to 127`) are represented using `1 byte`.
- Characters outside the __ASCII range__ (`128 to 1114111`) are represented using `2 to 4 bytes`.

`Data Representation`: The input data set is represented as a list of integers, 
where each integer represents __1 byte of data__. 
Only the 8 least significant bits of each integer need to be considered.

__Implementation Details__

- `Iterating Through Data`: The function iterates through the integers in the input list, examining each byte.

- `Checking Leading Bits`: For each integer, the function checks the leading bits to determine the character length:

1) If the leading bit is `0`, it's a __1-byte character__.
2) If the leading bits are `110`, it's a __2-byte character__.
3) If the leading bits are `1110`, it's a __3-byte character__.
4) If the leading bits are `11110`, it's a __4-byte character__.
5) If the leading bit is `10`, it's a __continuation byte__.

- `Validating Continuation Bytes`: If a character is more than __1 byte long__, the function ensures that the next bytes start with `10`.

- `Handling Edge Cases`: The function takes care of cases where the number of __continuation bytes__ 
is incorrect or the data set contains invalid byte sequences.

__For Instance__:

- `Input`: [197, 130, 1]
- `First Byte` (197): Binary representation: `11000101`. Indicates a 2-byte character. Valid.
- `Second Byte` (130): Binary representation: `10000010`. Indicates a continuation byte. Valid.
- `Third Byte` (1): Binary representation: `00000001`. Indicates a 1-byte character. Valid.

__The input represents a valid UTF-8 encoding__.

```
result = validUTF8([197, 130, 1])
print(result)  # Output: True

```

