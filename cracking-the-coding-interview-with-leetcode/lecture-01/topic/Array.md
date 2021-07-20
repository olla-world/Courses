## Arrays

An array is a collection of items stored at contiguous memory locations, each identifed by at least one __array index or key__. The index of an array of size N can range from 0 to N-1.

**Note:** Python does not have built-in support for arrays, but Python Lists can be used instead.

Create an array containing mango names:
`mangoes = ['umrupali', 'langra', 'fazli']`
Access a single element of array:
`m = mangoes[0]`
Modify the value of the first array item:
`mangoes[0] = 'Hari bhanga'`
Use the __len()__ method to return the length of an array
`l = len(mangoes)`
You can use the __for in__ loop to loop through all the elements of an array. Print each item in the mangoes array:

```Python
    for m in mangoes:
        print(m)
```
