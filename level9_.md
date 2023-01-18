# Question 1:
Write a Python program to find the size of a singly linked list.

```python
class Node:
    # Singly linked node
    def __init__(self, data=None):
        self.data = data
        self.next = None
class singly_linked_list:
    def __init__(self):
        # Createe an empty list
        self.tail = None
        self.head = None
        self.count = 0
	
    def append_item(self, data):
        #Append items on the list
        node = Node(data)
        if self.head:
            self.head.next = node
            self.head = node
        else:
            self.tail = node
            self.head = node
        self.count += 1
    
    def iterate_item(self):
        # Iterate the list.
        current_item = self.tail
        while current_item:
            val = current_item.data
            current_item = current_item.next
            yield val

items = singly_linked_list()
items.append_item('PHP')
items.append_item('Python')
items.append_item('C#')
items.append_item('C++')
items.append_item('Java')

print("Original list:")
for val in items.iterate_item():
    print(val)

print("\nSize of the list:",items.count)
```
Test case:
> Input: PHP<br>Python <br>C#<br> C++ <br> Java 

>Output: Size of the list: 5

Test case 2:
>Input: Apple<br> Mango<br> Pineapple

>Output: Size of the list: 3


# Question 2:

Write a Python program to search a specific item in a singly linked list and return true if the item is found otherwise return false.

```python
#Solution
class Node:
    # Singly linked node
    def __init__(self, data=None):
        self.data = data
        self.next = None
class singly_linked_list:
    def __init__(self):
        # Createe an empty list
        self.tail = None
        self.head = None
        self.count = 0

    def append_item(self, data):
        #Append items on the list
        node = Node(data)
        if self.head:
            self.head.next = node
            self.head = node
        else:
            self.tail = node
            self.head = node
        self.count += 1
    
    def iterate_item(self):
        # Iterate the list.
        current_item = self.tail
        while current_item:
            val = current_item.data
            current_item = current_item.next
            yield val

    def search_item(self, val):
         # Search the list
         for node in self.iterate_item():
             if val == node:
                 return True
         return False

items = singly_linked_list()
items.append_item('PHP')
items.append_item('Python')
items.append_item('C#')
items.append_item('C++')
items.append_item('Java')

a=input("Enter the Item to find: ")
if items.search_item(a):
    print("True")
else:
    print("False")
```

Test case 1:
>Input: Enter the Item to find: SQL

>Output: False

Test case 2:
>Input: Enter the Item to find: Java

>Output: True


# Question 3:

Write a Python program to access a specific item in a singly linked list using index value.

```Python 
#Solution
class Node:
    # Singly linked node
    def __init__(self, data=None):
        self.data = data
        self.next = None
class singly_linked_list:
    def __init__(self):
        # Createe an empty list
        self.tail = None
        self.head = None
        self.count = 0
	
    def append_item(self, data):
        #Append items on the list
        node = Node(data)
        if self.head:
            self.head.next = node
            self.head = node
        else:
            self.tail = node
            self.head = node
        self.count += 1
    
    def __getitem__(self, index):
        if index > self.count - 1:
            return "Index out of range"
        current_val = self.tail
        for n in range(index):
            current_val = current_val.next
        return current_val.data


items = singly_linked_list()
items.append_item('PHP')
items.append_item('Python')
items.append_item('C#')
items.append_item('C++')
items.append_item('Java')

n=int(input("Enter the Index to search: "))
print("The element at Index",n,"is",items[n])

```
Test case 1:
>Input: Enter the Index to search: 2

>Output: The element at Index 2 is C#

Test case 2:

>Input: Enter the Index to search:0

>Output:The element at Index 0 is PHP

Test case 3:

>Input: Enter the Index to search: 10

>Output: The element at Index 10 is Index out of range


# Question 4:
Write a Python program to create a Balanced Binary Search Tree (BST) using an array (given) elements where array elements are sorted in ascending order.

```python
#Solution
class TreeNode(object):
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

def sorted_array_to_bst(nums):
    
    if not nums:
        return None
    mid_val = len(nums)//2
    node = TreeNode(nums[mid_val])
    node.left = sorted_array_to_bst(nums[:mid_val])
    node.right = sorted_array_to_bst(nums[mid_val+1:])
    return node

def preOrder(node): 
    if not node: 
        return      
    print(node.val)
    preOrder(node.left) 
    preOrder(node.right)   
    
result = sorted_array_to_bst([1, 2, 3, 4, 5, 6, 7])
preOrder(result)
```

Test case 1:
>Input: Given array: [1, 2, 3, 4, 5, 6, 7]

>Output: 4
2
1
3
6
5
7

Test case 2:

>Input: Given array: [2, 4, 6, 8, 10, 12]

>Output: 8
4
2
6
12
10


# Question 5:

Write a Python program to find the kth smallest element in a given a binary search tree.

```python
#Solution
class TreeNode(object):
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

def kth_smallest(root, k):
    stack = []
    while root or stack:
        while root:
            stack.append(root)
            root = root.left
        root = stack.pop()
        k -= 1
        if k == 0:
            break
        root = root.right
    return root.val

root = TreeNode(8)  
root.left = TreeNode(5)  
root.right = TreeNode(14) 
root.left.left = TreeNode(4)  
root.left.right = TreeNode(6) 
root.left.right.left = TreeNode(8)  
root.left.right.right = TreeNode(7)  
root.right.right = TreeNode(24) 
root.right.right.left = TreeNode(22)  
n = int(input('Enter the value of k:'))
print(kth_smallest(root, n))

```
Test case 1:
>Input: Enter the value of k: 1

>Output: 4

Test case 2: 
>Input: Enter the value of k: 4

>Output: 6

Test case 3:
>Input: Enter the value of k: 5

>Output: 6
