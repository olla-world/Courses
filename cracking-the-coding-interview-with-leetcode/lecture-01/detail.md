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

From this, we can conclude that the number of operations will be the same as the length of the array in the worst case. When the length of array is __n__, thime complexity will be __O(n)__

Now we want to reverse the given array

```Python
    numbers = [2, 5, 3, 7, 4]
    numbers_index = len(numbers) - 1
    result = []

    while(numbers_index>=0)
        result.append(numbers[numbers_index])
        numbers_index = numbers_index - 1 

    return result
```

Here this while loop will run n times , where n is equal to the length of the array. So, number of operations will be n and the time complexity will be __O(n)__. Beside this we need a new array(__result__) which has same number of elements as __numbers__ array. For this, the memory complexity will be __O(n)__

We can improve our solution

```Python
    numbers = [2, 5, 3, 7, 4]
    numbers_index = len(numbers) - 1
    start = 0
    end = numbers_index

    while(end>start)
        temp = numbers[end]
        numbers[end] = numbers[start]
        numbers[start] = temp
        end = end - 1
        start = start + 1

    return numbers
```

Now we don't need extra array, memory space remain constant. Memory complexity will be __O(1)__.
While loop will run n/2 times where length of the array is equal to the n. So the complexity will be __O(n/2)__ 