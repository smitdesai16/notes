# Array

An array is a collection of items stored at contiguous memory locations. The idea is to store multiple items of the same type together. This makes it easier to calculate the position of each element by simply adding an offset to a base value, i.e., the memory location of the first element of the array (generally denoted by the name of the array).

## One Dimentional Array

In this array contains only one row for storing the values. All values of this array are stored contiguously starting from 0 to the array size.

```c#
// Initilization of an empty array
int[] numbers1 = new int[4];

// Initilization of an array with elements
int[] numbers2 = new int[] { 2, 4, 5 };

// Setting new value
numbers2[2] = 5;
```

## Multi Dimentional Array

The multi-dimensional array contains more than one row to store the values. It is also known as a Rectangular Array in C# because it's each row length is same.

```c#
// Initilization of an 2 dimentional array
int[,] intarray = new int[4, 2];

// Initilization of an 3 dimentional array
int[,,] intarray1 = new int[4, 2, 3];

// Initilization of an array with elements
int[,] intarray = new int[,] { { 1, 2 }, { 3, 4 },  { 5, 6 },  { 7, 8 } };

// Setting new value
numbers2[2] = 5;
```

## Jagged Arrays

An array whose elements are arrays is known as Jagged arrays it means “array of arrays“. The jagged array elements may be of different dimensions and sizes.


```c#
// Initilization of an 2 dimentional array
int[][] arr = new int[2][];

arr[0] = new int[5] { 1, 3, 5, 7, 9 };
arr[1] = new int[4] { 2, 4, 6, 8 };
```

## Clone Array

```c#
int[] b = (int[]) a.Clone();
```

## Copy Array

```c#
// From Array, From Index, To Array, To's Start Index, From's Elements Till
Array.Copy(a, 0, b, 0, a.Length);
```
## Applications

- [1. Two Sum](/leetcode/1.md)
- [56. Merge Intervals](/leetcode/56.md)
- [42. Trapping Rain Water](/leetcode/42.md)
- [560. Subarray Sum Equals K](/leetcode/560.md)
- [200. Number of Islands](/leetcode/200.md)
- [4. Median of Two Sorted Arrays](/leetcode/4.md)
- [121. Best Time to Buy and Sell Stock](/leetcode/121.md)
- [53.Maximum Subarray](/leetcode/53.md)