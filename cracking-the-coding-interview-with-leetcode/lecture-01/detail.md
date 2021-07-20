## Arrays

An array is a collection of items stored at contiguous memory locations, each identifed by at least one __array index or key__. The index of an array of size N can range from 0 to N-1.

**Note:** Python does not have built-in support for arrays, but Python Lists can be used instead.

Create an array containing mango names:

```Python
    mangoes = ['umrupali', 'langra', 'fazli']
```

Access a single element of array:

```Python
    m = mangoes[0]
```

Modify the value of the first array item:

```Python
    mangoes[0] = 'Hari bhanga'
```

Use the __len()__ method to return the length of an array

```Python
    l = len(mangoes)
```

You can use the __for in__ loop to loop through all the elements of an array. Print each item in the mangoes array:

```Python
    for m in mangoes:
        print(m)
```


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
