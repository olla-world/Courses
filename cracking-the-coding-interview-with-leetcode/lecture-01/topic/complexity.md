## Time Complexity

The time complexity is the number of operations an algorithm performs to complete its task(__considering that each operation takes the same amount of time__).

**Note:** The algorithm that performs the task in the smallest number of operations is considered the most efficient one in the terms of the time complexity.

### Linear Search

Assume we have an given array and a value. Now we have to find the value in the array

```Python
    numbers = [2, 5, 3, 7, 4]
    target = 4

    for number in numbers
        if number == target
            return True
    return False
```

Here we need 5 operations to get the __target__ value. These are the maximum number of operations for the array, in the case of Linear search, this is also known as the worst case of an algorithm.

From this, we can conclude that the number of operations will be the same as the length of the array in the worst case.
