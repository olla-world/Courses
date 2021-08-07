# Arrays and Complexity

## Arrays

An array is a collection of items stored at contiguous memory locations, each identifed by at least one array `index or key`. The index of an array of size N can range from 0 to N-1.

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

Use the `len()` method to return the length of an array

```Python
    l = len(mangoes)
```

You can use the `for in` loop to loop through all the elements of an array. Print each item in the mangoes array:

```Python
    for m in mangoes:
        print(m)
```

## Time complexity

The time complexity is the number of operations an algorithm performs to complete its task _(considering that each operation takes the same amount of time)_.

**Note:** The algorithm that performs the task in the smallest number of operations is considered the most efficient one in the terms of the time complexity.

## Coding exercise

Assume we have an given array and a value. Now we have to find the value in the array

```Python
    numbers = [2, 5, 3, 7, 4]
    target = 4

    for number in numbers
        if number == target
            return True
    return False
```

Here we need 5 operations to get the `target` value. These are the maximum number of operations for the array, in the case of Linear search, this is also known as the worst case of an algorithm.

From this, we can conclude that the number of operations will be the same as the length of the array in the worst case. When the length of array is `n`, thime complexity will be `O(n)`

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

Here this while loop will run n times , where n is equal to the length of the array. So, number of operations will be n and the time complexity will be `O(n)`. Beside this we need a new array _(result)_ which has same number of elements as `numbers` array. For this, the memory complexity will be `O(n)`

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

Now we don't need extra array, memory space remain constant. Memory complexity will be `O(1)`.
`While loop` will run n/2 times where length of the array is equal to the n. So the complexity will be `O(n/2)`.

## Home work solutions

- **[Two Sum](https://leetcode.com/problems/two-sum/)**

  - **1st Solution**

    ```Python
        class solution:
            def twoSum(self, nums, target):
                length = len(nums)
                for i in range(length):
                    for j in range(i + 1, length):
                        if nums[i] + nums[j] == target:
                            return [i, j]
    ```

    > Time Complexity: `O(n^2)`.
    >
    > Memory Complexity: `O(1)`.

  - **2nd Solution**

    ```Python
        class solution:
            def twoSum(self, nums, target):
                hash_table = dict()
                length = len(nums)

                for i in range(length):
                    diff = target - nums[i]
                    if diff in hash_table:
                        return [i, hash_table[diff]]
                    else:
                        hash_table[nums[i]] = i
    ```

    > Time Complexity: `O(n)`.
    >
    > Memory Complexity: `O(n)`.
