# Question 1:
Write a Python program to create an array of 5 integers and display the array items. Access individual element through indexes by taking the index as input from user.

``` python
#solution
from array import *

array_num = array('i', [1,3,5,7,9])

for i in array_num:
    print(i)

x=int(input("Enter the index:"))
print('Your element is ',array_num[x])

```
Test case 1:
>Input: 0

>Output: Your element is 1

Test case 2:
>Input: 2

>Output: Your element is 5

Test case 3:
>Input: 4

>Output: Your element is 9

<br><br>


# Question 2:

Write a Python program to append a new item to the end of the array and print the appended array.

``` python
#solution
from array import *
array_num = array('i', [2, 6, 0, 9, 7])
x=int(input("Enter the number you want to append"))
array_num.append(x)
print("Appended array: "+str(array_num))
```

Test case 1:
>Input: 5

>Output: Appended array: array('i', [2, 6, 0, 9, 7, 5])

Test case 2:
>Input: 0

>Output:Appended array: array('i', [2, 6, 0, 9, 7, 0])

Test case 3:
>Input: 9

>Output: Appended array: array('i', [2, 6, 0, 9, 7, 9])

<br><br>

# Question 3:

Write a Python program to reverse the order of the items in an array of 5 elements. Prompt the user to input the elements of the array.

``` python
#solution
from array import *
arr = list(map(int, input("Enter 5 elements of the array").split()))
print("Original array: "+str(arr))
arr.reverse()
print("Reverse the order of the items:")
print(str(arr))
```
Test case 1:

>Input: 4 7 5 9 6

>Output: Reverse the order of the items:
[6, 9, 5, 7, 4]

Test case 2:

>Input: 7 14 3 7 9

>Output: Reverse the order of the items:
[9, 7, 3, 14, 7]

Test case 3:
>Input: 0 16 78 33 67

>Output: Reverse the order of the items:
[67, 33, 78, 16, 0]

<br><br>

# Question 4:

Write a Python program to get the length in bytes of one array item in the internal representation, Given array is [1, 3, 5, 7, 9] .

``` python
#solution
from array import *
array_num = array('i', [1, 3, 5, 7, 9])
print("Original array: "+str(array_num))
print("Length in bytes of one array item: "+str(array_num.itemsize))
```

>Output:
Length in bytes of one array item: 4

<br><br>

# Question 5:

Write a Python program to get the current memory address and the length in elements of the buffer used to hold an array's contents and also find the size of the memory buffer in bytes

```python
#Solution
from array import *
array_num = array('i', [1, 3, 5, 7, 9])
print("Original array: "+str(array_num))
print("Current memory address and the length in elements of the buffer: "+str(array_num.buffer_info()))
print("The size of the memory buffer in bytes: "+str(array_num.buffer_info()[1] * array_num.itemsize))
```

Test 1:

>Output: Original array: array('i', [1, 3, 5, 7, 9])<br>
Current memory address and the length in elements of the buffer: (139741883429512, 5)<br>
The size of the memory buffer in bytes: 20

<br>

# Question 6

Write a Python program to get the number of occurrences of a specified element in an array.

``` python 
from array import *
array_num = array('i', [1, 3, 1, 3, 7, 9, 3])
x=int(input("Enter the number to check occurence:"))
print("Number of occurrences of the number",x, "in the said array: "+str(array_num.count(x)))
```
Test case 1:
>Input: 3

>Output: Number of occurrences of the number 3 in the said array: 3

Test case 2:
 >Input: 1

 >Output:Number of occurrences of the number 1 in the said array: 2

 Test case 3:
 >Input: 9

 >Output: Number of occurrences of the number 9 in the said array: 1

 <br>

 # Question 7:

Write a Python program to append an array with elements of another array. Take the elements of other array as input from user.
``` python
#solution
from array import *
array_num = array('i', [1, 3, 5, 7, 9])
array_append = list(map(int, input("Enter elements of the array to append").split()))
array_num.extend(array_append)
print("Extended array: "+str(array_num))

```
Test case 1:
>Input: 2 4 6 8 10

>Output: Extended array:  array('i', [1, 3, 5, 7, 9, 2, 4, 6, 8, 10])

Test case 2:
>Input: 5 6 3 7 32 

>Output:
Extended array:  array('i', [1, 3, 5, 7, 9, 5, 6, 3, 7, 32])

<br><br>

# Question 8:

Write a Python program to remove the first occurrence of a specified element from an array.

```python
#solution
from array import *
array_num = array('i', [1, 3, 5, 3, 7, 1, 9, 3])
x=int(input("Enter the number whose first occurance you want to remove:"))
array_num.remove(x)
print("New array: "+str(array_num))
```
Test case 1:
>Input: 3

>Output:New array: array('i', [1, 5, 3, 7, 1, 9, 3])

Test case 2:
>Input: 5

>Output: New array: array('i', [1, 3, 3, 7, 1, 9, 3])

<br><br>

# Question 9:
Take an integer array as input from user and check if that array of integers contain duplicate elements. Return true if any value appear at least twice and return false if every element is distinct.

```python
#solution
def test_duplicate(array_nums):
    nums_set = set(array_nums)    
    return len(array_nums) != len(nums_set)     
arr = list(map(int, input("Enter 5 elements of the array").split()))
print(test_duplicate(arr))
```

Test case 1:
>Input: 5 4 6 4 3 

>Output: True

Test case 2:
>Input: 3 6 8 4 1

>Output: False

Test case 3:
>Input: 6 9 2 5 0

>Output: False

<br><br>

# Question 10:

Write a Python program to find the first duplicate element in a given array of integers. Return -1 If there are no such elements. Take array as an input from user.

```python
def find_first_duplicate(nums):
    num_set = set()
    no_duplicate = -1

    for i in range(len(nums)):

        if nums[i] in num_set:
            return nums[i]
        else:
            num_set.add(nums[i])

    return no_duplicate

arr = list(map(int, input("Enter 5 elements of the array").split()))

print(find_first_duplicate(arr))
```
Test case 1:
>Input: 1 3 5 7 7 

>Output: 7

Test case 2:
>Input: 6 4 4 7 9

>Output: 4

Test case 3:
>Input: 4 6 -8 -8 0

>Output: -8

<br> <br>

# Question 11: 
Write a python program to find the index of the element given by the user present in that array.

```python
def search(list,key):
    for i in range(len(list)):
        if list[i]==key:
            return i
    return -1
list = [8,2,34,15,76,0]
key = int(input("Enter the key:"))
index = search(list,key)
if(index==-1):
    print("The element is not present in the array")
else:
    print('The index of the key is',index)

```
Test case 1:
>Input: Enter the key: 34

>Output: The index of the key is 2

Test case 2:
>Input: Enter the key: 0

>output: The index of the key is 5

Test case 3:
>Input: Enter the key: 9

>Output: The element is not present in the array

<br><br>

# Question 12:

Write a Python program to find a pair with highest product from a given array of integer.Input the array from the user

```python
#solution
def max_Product(arr): 
    arr_len = len(arr) 
    if (arr_len < 2): 
        print("No pairs exists") 
        return      
    # Initialize max product pair 
    x = arr[0]; y = arr[1] 

    # Traverse through every possible pair     
    for i in range(0, arr_len): 

        for j in range(i + 1, arr_len): 
            if (arr[i] * arr[j] > x * y): 
                x = arr[i]; y = arr[j] 

    return x,y    

arr = list(map(int, input("Enter elements of the array:").split())) 
print("Original array:", arr)
print("Maximum product pair is:", max_Product(arr))

```
Test case 1:
>Input: Enter the elements of array: 6 3 8 9 4 0

>output: Original array: [6, 3, 8, 9, 4, 0]<br>
Maximum Product pair is: (8,9)

Test case 2:
>Input: Enter the elements of array: 0 3 7 3 6 5

>Output: Original array: [0, 3, 7, 3, 6, 5]<br>
Maximum Product pair is: (7,6)

<br><br>

# Question 13:
Write a Python program to find the missing number in a given array of numbers between 10 and 20.

```python
#solution
import array as arr
def test(nums):
    return sum(range(10, 21)) - sum(list(nums))

array_num = arr.array('i', [10, 11, 12, 13, 14, 16, 17, 18, 19, 20])
print("Original array:")
for i in range(len(array_num)):    
    print(array_num[i], end=' ')
print("\nMissing number in the said array (10-20): ",test(array_num))
 
array_num = arr.array('i', [10, 11, 12, 13, 14, 15, 16, 17, 18, 19])
print("\nOriginal array:")
for i in range(len(array_num)):    
    print(array_num[i], end=' ')
print("\nMissing number in the said array (10-20): ",test(array_num))
```
>Output: Original array:
10 11 12 13 14 16 17 18 19 20 <br>
Missing number in the said array (10-20):  15<br>
Original array:
10 11 12 13 14 15 16 17 18 19 <br>
Missing number in the said array (10-20):  20

<br><br>

# Question 14:
Write a Python program to remove all duplicate elements from a given array and returns a new array.

``` python
#solution
import array as arr
def test(nums):
    return sorted(set(nums),key=nums.index)

array_num = list(map(int, input("Enter elements of the array").split()))
print("Original array:")
for i in range(len(array_num)):    
    print(array_num[i], end=' ')
print("\nAfter removing duplicate elements from the said array:")
result = arr.array('i', test(array_num))
for i in range(len(result)):    
    print(result[i], end=' ')


```

Test case 1:
>Input:5 7 5 4 7 8

>Output: After removing duplicate elements from the said array: 5 7 4 8 

Test case 2:
>Input: 5 6 6 5 4 9 

>Output: After removing duplicate elements from the said array: 5 6 4 9

Test case 3:
>Input: 2 0 5 3 6

>Output:After removing duplicate elements from the said array: 2 0 5 3 6

<br>

# Question 15

Given an array which may contain duplicates, print all elements and their frequencies.

``` python
#Solution

def countFreq(arr, n):
     
    visited = [False for i in range(n)]
 
    for i in range(n):
         
        if (visited[i] == True):
            continue
 
        count = 1
        for j in range(i + 1, n, 1):
            if (arr[i] == arr[j]):
                visited[j] = True
                count += 1
         
        print(arr[i], count)
 
if __name__ == '__main__':
     arr = list(map(int, input("Enter elements of the array").split()))

    n = len(arr)
    countFreq(arr, n)
     
``` 
Test case 1:
>Input : Enter elements of array: 10 20 20 10 10 20 5 20

>Output : 10 3<br>
         20 4  <br>
         5  1 <br>

Test case 2:
>Input: Enter elements of array: 0 3 6 0 9 5 5 

>Output: 0 2 <br> 3 1 <br>6 1<br>9 1<br> 5 2

<br>

# Question 16

Find minimum and maximum element in an array

```python
class pair:
    def __init__(self):
        self.min = 0
        self.max = 0
 
def getMinMax(arr: list, n: int) -> pair:
    minmax = pair()
 
    # If there is only one element then return it as min and max both
    if n == 1:
        minmax.max = arr[0]
        minmax.min = arr[0]
        return minmax
 
    # If there are more than one elements, then initialize min
    # and max
    if arr[0] > arr[1]:
        minmax.max = arr[0]
        minmax.min = arr[1]
    else:
        minmax.max = arr[1]
        minmax.min = arr[0]
 
    for i in range(2, n):
        if arr[i] > minmax.max:
            minmax.max = arr[i]
        elif arr[i] < minmax.min:
            minmax.min = arr[i]
 
    return minmax

    # Driver Code
if __name__ == "__main__":
    arr = list(map(int, input("Enter 6 elements of the array").split()))
    arr_size = 6
    minmax = getMinMax(arr, arr_size)
    print("Minimum element is", minmax.min)
    print("Maximum element is", minmax.max)
```
Test case 1:
>Input: Enter 6 elements of the arrray: 5 7 8 3 6 77

>Output:Minimum element is 3<br>
Maximum element is 77

Test case 2:
>Input: Enter the 6 elements of the array: 0 4 66 33 56 7

Output:
Minimum element is 0<br>
Maximum element is 66

<br><br>

# Question 17:
Given an array of N integers, and a number sum, the task is to find the number of pairs of integers in the array whose sum is equal to sum.

```python
#Solution
def getPairsCount(arr, n, sum):
 
    count = 0  # Initialize result
 
    # Consider all possible pairs
    # and check their sums
    for i in range(0, n):
        for j in range(i + 1, n):
            if arr[i] + arr[j] == sum:
                count += 1
 
    return count
 
 
# Driver function
arr = list(map(int, input("Enter elements of the array:").split()))
n = len(arr)
sum = int(input("Enter the sum:"))
print("Count of pairs is",
      getPairsCount(arr, n, sum))
```

Test case 1:

>Input: Enter elements of the array: 1 5 7 -1 5<br>
Enter the sum: 6

>Output: Count of pair is 3

Test case 2:
>Input: Enter elements of the array: 3 65 5 6 72 4 <br>
Enter the sum: 9

>Output: Count of pair is 2

Test case 3:
>Input: Enter elements of the array: 2 -5 7 9 0 1<br>
Enter the sum: 12

>Output: Count of pair is 0

<br><br>

# Question 18:

Given three arrays sorted in non-decreasing order, print all common elements in these arrays.
Array 1 = {1, 5, 10, 20, 40, 80} <br>
Array 2 = {6, 7, 20, 80, 100} <br>
Array 3 = {3, 4, 15, 20, 30, 70, 80, 120} 


```Python
def findCommon(ar1, ar2, ar3, n1, n2, n3):

    i, j, k = 0, 0, 0

    while (i < n1 and j < n2 and k < n3):

        if (ar1[i] == ar2[j] and ar2[j] == ar3[k]):
            print (ar1[i])
            i += 1
            j += 1
            k += 1
 
        # x < y
        elif ar1[i] < ar2[j]:
            i += 1
 
        # y < z
        elif ar2[j] < ar3[k]:
            j += 1

        else:
            k += 1
            
ar1 = [1, 5, 10, 20, 40, 80]
ar2 = [6, 7, 20, 80, 100]
ar3 = [3, 4, 15, 20, 30, 70, 80, 120]
n1 = len(ar1)
n2 = len(ar2)
n3 = len(ar3)
print ("Common elements are")
findCommon(ar1, ar2, ar3, n1, n2, n3)
```
>Input: <br>
ar1[] = {1, 5, 10, 20, 40, 80} <br>
ar2[] = {6, 7, 20, 80, 100} <br>
ar3[] = {3, 4, 15, 20, 30, 70, 80, 120} 

>Output: Common elements are<br>20, 80

<br><br>

# Question 19:

Given an array where every element occurs three times, except one element which occurs only once. Find the element that occurs once

```Python
#Solution
def getSingle(arr, n):
    ones = 0
    twos = 0
     
    for i in range(n):

        twos = twos ^ (ones & arr[i])

        ones = ones ^ arr[i]

        common_bit_mask = ~(ones & twos)

        ones &= common_bit_mask
         
        twos &= common_bit_mask
    return ones
    
arr = list(map(int, input("Enter elements of the array:").split()))
n = len(arr)
print("The element with single occurrence is ",
        getSingle(arr, n))
```
Test case 1:
>Input: Enter elements of the array: 12 1 12 3 12 1 1 2 3 3 

>Output: The element with single occurrence is  2

Test case 2:
>Input: Enter elements of the array: 10 20 10 30 10 30 30

>Output: The elements with single occurence is 20

<br><br>

# Question 20:
Given an unsorted array that contains even number of occurrences for all numbers except two numbers. Find the two numbers which have odd occurrences 

``` python
# solution
def printTwoOdd(arr, size):

    xor2 = arr[0]

    set_bit_no = 0 
    n = size - 2
    x, y = 0, 0

    for i in range(1, size):
        xor2 = xor2 ^ arr[i]

    set_bit_no = xor2 & ~(xor2 - 1)

    for i in range(size):

        if(arr[i] & set_bit_no):
            x = x ^ arr[i]
            
        else:
            y = y ^ arr[i]
 
    print("The two elements with odd occurence are", x, "&", y)
 
arr = list(map(int, input("Enter elements of the array:").split()))
arr_size = len(arr)
printTwoOdd(arr, arr_size)
```

Test case 1: 
>Input: Enter elements of the array: 4 2 4 5 2 3 3 1

>Output:The two elements with odd occurence are 5 & 1

Test case 2:
>Input: Enter elements of the array: 12 23 34 12 12 23 12 45

>Output: The two elements with odd occurence are 34 & 45

Test case 3:
>Input: Enter elements of the array: 4 4 100 5000 4 4 4 4 100 100

>Output: The two elements with odd occurence are 100 & 5000

<br><br>

# Question 21:

Given an arrray of integers, print all its subarray. Subarray is any continuous part of an array

```python
#Solution
def printSubarray(arr):
    for i in range(0,len(arr)+1):
        start=i
        for j in range(i,len(arr)+1):
            end=j
            for k in range(start,end):
                print(arr[k],end=" ")

            print()

        print()
arr=list(map(int, input("Enter elements of the array:").split()))
printSubarray(arr)

```

Test case 1:
>Input: Enter elements of the array: 2 4 6 8 10<br>
>Output: <br>
2<br>
2 4<br>
2 4 6<br>
2 4 6 8<br>
2 4 6 8 10<br>
<br>
4<br>
4 6<br>
4 6 8<br>
4 6 8 10<br>
<br>
6<br>
6 8<br>
6 8 10<br>
<br>
8<br>
8 10<br>
<br>
10<br>

Test case 2:
>Input: Enter elements of the array: 3 6 4 7<br>
>Output: <br>3<br>
3 6<br>
3 6 4<br>
3 6 4 7<br>
<br>
6<br>
6 4<br>
6 4 7<br>
<br>
4<br>
4 7<br>
<br>
7

<br><br>

# Question 22:
Take Matrix input from user in Python with specified number of rows and columns and print the Matrix
``` python
#solution
def get_matrix():
  # Get the dimensions of the matrix
  rows = int(input("Enter the number of rows: "))
  cols = int(input("Enter the number of columns: "))

  # Initialize the matrix
  matrix = []

  # Get the matrix elements from the user
  for i in range(rows):
    a = []
    for j in range(cols):
      a.append(int(input("Enter the element for row {} and column {}: ".format(i+1, j+1))))
    matrix.append(a)

  return matrix

# Test the function
matrix = get_matrix()
print(matrix)
```
Test Case:
>Input: Enter number of Rows: 3<br>Enter number of columns:3<br>
Enter the element for row 1 and column 1:  1<br>
Enter the element for row 1 and column 2:  4<br>
Enter the element for row 1 and column 3:  5<br>
 <br>
Enter the element for row 2 and column 1:  3<br>
Enter the element for row 2 and column 2:  6<br>
Enter the element for row 2 and column 3:  4<br>
 <br>
Enter the element for row 3 and column 1: 4<br>
Enter the element for row 3 and column 2: 3<br>
Enter the element for row 3 and column 3: 5<br>

>Output:[[1, 4, 5], [3, 6, 4], [4, 3, 5]]

<br><br>

# Question 23:

Print a given matrix in its spiral form

```python
def print_matrix_spiral(matrix):
  # Get the number of rows and columns in the matrix
  rows = len(matrix)
  cols = len(matrix[0])

  # Initialize the row and column indices
  row = 0
  col = 0

  # Initialize the direction of the spiral
  # 0: right, 1: down, 2: left, 3: up
  direction = 0

  # Initialize the visited cells set
  visited = set()

  # Iterate until all cells are visited
  while len(visited) < rows * cols:
    # Print the current cell
    print(matrix[row][col], end=" ")

    # Mark the current cell as visited
    visited.add((row, col))

    # Update the row and column indices based on the direction
    if direction == 0:
      col += 1
      if col == cols or (row, col) in visited:
        col -= 1
        row += 1
        direction = 1
    elif direction == 1:
      row += 1
      if row == rows or (row, col) in visited:
        row -= 1
        col -= 1
        direction = 2
    elif direction == 2:
      col -= 1
      if col < 0 or (row, col) in visited:
        col += 1
        row -= 1
        direction = 3
    elif direction == 3:
      row -= 1
      if row < 0 or (row, col) in visited:
        row += 1
        col += 1
        
matrix = [[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]]
print_matrix_spiral(matrix)
```

>Input:<br> [[1, 2, 3],<br>
          [4, 5, 6],<br>
          [7, 8, 9]]

>Output: 1 2 3 6 9 8 7 4 5

<br><br>

# Question 24:
 Write a python program to print the elements of a given matrix in row-wise and column-wise

 ```python
 #Solution

 matrix = [[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]]

# Print the matrix row-wise
for row in matrix:
    print(row)

# Print the matrix column-wise
for i in range(len(matrix[0])):
    column = [row[i] for row in matrix]
    print(column)

 ```
 Test Case 1: 
 >Input: Matrix= [[1, 2, 3],<br>
          [4, 5, 6], <br>
          [7, 8, 9]]

>Output: [1, 2, 3]<br>
[4, 5, 6]<br>
[7, 8, 9]<br>
[1, 4, 7]<br>
[2, 5, 8]<br>
[3, 6, 9]


Test Case 2:
>Input: Matrix = [[9, 8, 7],<br>
          [6, 5, 4], <br>
          [3, 2, 1]]

>Output: [9, 8, 7]<br>
[6, 5, 4]<br>
[3, 2, 1]<br>
[9, 6, 3]<br>
[8, 5, 2]<br>
[7, 4, 1]

<br><br>

# Question 25:

Write a python program to print a matrix in counter clock wise spiral form.

```python
#solution
R = 4
C = 4

def counterClockspiralPrint(m, n, arr) :
    k = 0; l = 0

    cnt = 0

    total = m * n
 
    while (k < m and l < n) :
        if (cnt == total) :
            break

        for i in range(k, m) :
            print(arr[i][l], end = " ")
            cnt += 1
         
        l += 1
 
        if (cnt == total) :
            break

        for i in range (l, n) :
            print( arr[m - 1][i], end = " ")
            cnt += 1
         
        m -= 1
         
        if (cnt == total) :
            break

        if (k < m) :
            for i in range(m - 1, k - 1, -1) :
                print(arr[i][n - 1], end = " ")
                cnt += 1
            n -= 1
 
        if (cnt == total) :
            break

        if (l < n) :
            for i in range(n - 1, l - 1, -1) :
                print( arr[k][i], end = " ")
                cnt += 1
                 
            k += 1

arr = [ [ 1, 2, 3, 4 ],
        [ 5, 6, 7, 8 ],
        [ 9, 10, 11, 12 ],
        [ 13, 14, 15, 16 ] ]
         
counterClockspiralPrint(R, C, arr)
```
>Input: [ [ 1, 2, 3, 4 ],
        [ 5, 6, 7, 8 ],
        [ 9, 10, 11, 12 ],
        [ 13, 14, 15, 16 ] ]

>Output: 1 5 9 13 14 15 16 12 8 4 3 2 6 10 11 7

<br> <br>

# Question 26:
 
Given a matrix of 2D array of n rows and m columns. Print this matrix in ZIG-ZAG fashion as shown in figure. 

![image](https://media.geeksforgeeks.org/wp-content/cdn-uploads/matrix_zag-zag.png)

```python
matrix =[
            [ 1, 2, 3,],
            [ 4, 5, 6 ],
            [ 7, 8, 9 ],
        ]
rows=3
columns=3
   
solution=[[] for i in range(rows+columns-1)]
 
for i in range(rows):
    for j in range(columns):
        sum=i+j
        if(sum%2 ==0):
 
            #add at beginning
            solution[sum].insert(0,matrix[i][j])
        else:
 
            #add at end of the list
            solution[sum].append(matrix[i][j])
         
             
# print the solution as it as
for i in solution:
    for j in i:
        print(j,end=" ")
```

>Input: Matrix = [
            [ 1, 2, 3,],
            [ 4, 5, 6 ],
            [ 7, 8, 9 ],
        ]

>Output: 1 2 4 7 5 3 6 8 9 

<br><br>

# Question 27
You have given an integer matrix with odd dimensions. Find the square of the diagonal elements on both sides.

```python
#Solution
def diagonalsquare(mat, row, column) :
 
    print ("Diagonal one : ", end = "")
    for i in range(0, row) :
        for j in range(0, column) :

            if (i == j) :

                print ("{} ".format(mat[i][j] *
                                    mat[i][j]), end = "")

    print (" \nDiagonal two : ", end = "")
    for i in range(0, row) :
        for j in range(0, column) :

            if (i + j == column - 1) :

                print ("{} ".format(mat[i][j] *
                                    mat[i][j]), end = "")

matrix = [[ 2, 5, 7 ],
        [ 3, 7, 2 ],
        [ 5, 6, 9 ]]
diagonalsquare(matrix, 3, 3)
```
Test Case 1:

>Input: matrix = [[ 2, 5, 7 ],
        [ 3, 7, 2 ],
        [ 5, 6, 9 ]]

>Output = Diagonal one : 4 49 81  
Diagonal two : 49 49 25

Test Case 2:

>Input: matrix = [
            [ 1, 2, 3,],
            [ 4, 5, 6 ],
            [ 7, 8, 9 ],
        ]

>Output:Diagonal one : 1 25 81  
Diagonal two : 9 25 49 

<br><br>

# Question 28:
 
Write a python programm to add two matrices.

```python
#Solution

def add_matrices(matrix1, matrix2):
    # Check if the matrices are compatible for addition
    if len(matrix1) != len(matrix2) or len(matrix1[0]) != len(matrix2[0]):
        print("Error: Matrices are incompatible for addition")
        return

    # Add the matrices
    result = []
    for i in range(len(matrix1)):
        result.append([])
        for j in range(len(matrix1[0])):
            result[i].append(matrix1[i][j] + matrix2[i][j])

    return result

# Test the function
matrix1 = [[1, 2, 3],
           [4, 5, 6]]
matrix2 = [[7, 8, 9],
           [10, 11, 12]]
print(add_matrices(matrix1, matrix2))
```
Test case 1:
>Input: matrix1 = [[1, 2, 3],
           [4, 5, 6]]<br>
        matrix2 = [[7, 8, 9],
           [10, 11, 12]]

>Output = [[8, 10, 12], [14, 16, 18]]

Test case 2:

>Input: Matrix1= [[5, 7, 3],
           [28, 5, 9]]<br>
        Matrix2= [[7, 23, 0],
           [8, 64, 3]]

>Output: [[12, 30, 3], [36, 69, 12]]

<br><br>

# Question 29:

Write a python program to transpose a matrix.

Transpose of a matrix is obtained by changing rows to columns and columns to rows. In other words, transpose of A[N][M] is obtained by changing A[i][j] to A[j][i].

```python
#Solution
N = 4
 
# This function stores
# transpose of A[][] in B[][]
 
 
def transpose(A, B):
 
    for i in range(N):
        for j in range(N):
            B[i][j] = A[j][i]
 
 
# Driver code
if __name__ == '__main__':
  A = [[1, 1, 1, 1],
       [2, 2, 2, 2],
       [3, 3, 3, 3],
       [4, 4, 4, 4]]
 
 
  # To store result
  B = [[0 for x in range(N)] for y in range(N)]
 
  # Function call
  transpose(A, B)
 
  print("Result matrix is")
  for i in range(N):
      for j in range(N):
          print(B[i][j], " ", end='')
      print()
```
Test case 1:

>Input: Matrix=[[1, 1, 1, 1],
       [2, 2, 2, 2],
       [3, 3, 3, 3],
       [4, 4, 4, 4]]

>Output: <br>
Result matrix is<br>
1  2  3  4<br>
1  2  3  4<br>
1  2  3  4<br>
1  2  3  4<br>

Test case 2:
>Input:  Matrix=[[1, 2, 3, 4],
       [5, 6, 7, 8],
       [9, 10, 11, 12],
       [13, 14, 15, 16]]

>Output:<br> Result matrix is<br>
1  5  9  13<br>
2  6  10  14<br>
3  7  11  15<br>
4  8  12  16

<br><br>

# Question 30:

Swap an array using Bubble Sort method. Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. 

```python
#Solution
def bubbleSort(arr):
    n = len(arr)
    swapped = False
    for i in range(n-1):

        for j in range(0, n-i-1):
 

            if arr[j] > arr[j + 1]:
                swapped = True
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
         
        if not swapped:
            return
 
 
arr = [64, 34, 25, 12, 22, 11, 90]
 
bubbleSort(arr)
 
print("Sorted array is:")
for i in range(len(arr)):
    print("% d" % arr[i], end=" ")
```
Test Case 1:
>Input: arr=[64, 34, 25, 12, 22, 11, 90]

>Output: 11  12  22  25  34  64  90

Test Case 2:
>Input: arr= [0, 69, 7, 19, 56, 62, 99]

>Output:  0  7  19  56  62  69  99

Test Case 3: 
>Input: arr = [43, 6, 24, 78, 32, 8]

>Output: 6  8  24  32  43  78



### Submitted by Hrishabh Mishra