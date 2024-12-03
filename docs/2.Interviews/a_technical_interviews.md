# 🚀 The Ultimate Python Technical Interview Guide
![Software Engineer Interview](https://i.postimg.cc/BnTvjL3t/temp-Imageb-Xdn-Pv.avif)
## 📘 Introduction

Welcome to your comprehensive companion for mastering technical interviews! Whether you're aiming for FAANG companies or preparing for your first technical interview, this guide will help you tackle coding challenges with confidence.

### 🎯 Why This Guide?

-   🐍  **Python-Focused**: All solutions and examples in Python (the most popular interview language!)
-   🧠  **Pattern Recognition**: Learn to spot and solve common problem patterns
-   ⚡  **Optimization Skills**: Master the art of writing efficient code
-   🎓  **Interview Strategy**: Learn not just what to code, but how to approach problems
-   💪  **Practical Examples**: Real interview problems with detailed solutions

### 🎨 How This Guide is Different

We believe learning should be fun! You'll find:

-   🎮 Interactive examples
-   🎯 Pattern-based learning
-   🧩 Visual explanations
-   💡 "Aha!" moment highlights
-   🚫 Common pitfall warnings

## 🗺️ Guide Structure

### 1️⃣ Foundation Building

-   Big-O Notation and Complexity Analysis
-   Python-specific optimizations
-   Core data structures in Python
-   Essential algorithms and their implementations

### 2️⃣ Pattern Recognition

-   Common interview patterns
-   When to use which approach
-   Pattern-specific optimizations
-   Real interview problem mappings

### 3️⃣ Interview Strategy

-   Problem-solving framework
-   Communication tips
-   Code organization
-   Testing approaches

### Good References
[Technical Interview Github Repo](https://github.com/ashishps1/awesome-leetcode-resources?tab=readme-ov-file)

## 💻 Before We Begin: Python Essentials

### 🔧 Key Python Tools for Interviews
````python
# Common imports you'll need
from collections import defaultdict, deque, Counter
from heapq import heappush, heappop
from typing import List, Dict, Set
````
### 🛠️ Python-Specific Pro Tips
````python
# 1. List comprehension for cleaner code
squares = [x*x for x in range(10)]

# 2. Default dictionaries for counting
counter = defaultdict(int)

# 3. Built-in sort with custom key
items.sort(key=lambda x: x.value)

# 4. Multiple assignment
x, y = y, x  # Swap values
````
## 🎯 How to Use This Guide

### 📚 Learning Path

1.  **Build the Foundation**
    -   Master Python basics
    -   Understand complexity analysis
    -   Learn core data structures
2.  **Pattern Recognition**
    -   Study common patterns
    -   Practice similar problems
    -   Learn pattern variations
3.  **Problem Solving**
    -   Apply patterns to new problems
    -   Practice optimization
    -   Work on communication

### ⏰ Time Management

-   🌱  **Beginner**: 2-3 months of preparation
-   🌿  **Intermediate**: 1-2 months of focused practice
-   🌳  **Advanced**: 2-3 weeks of revision

## 🎮 Let's Get Started!

### 🎯 Your First Steps

1.  Review Python fundamentals
2.  Start with easy problems
3.  Focus on problem-solving process
4.  Practice explaining your thought process

### 💡 Remember

-   Understanding patterns > Memorizing solutions
-   Practice regularly > Cramming
-   Clear communication > Perfect code
-   Learning from mistakes > Getting it right first time

## 🚨 Common Interview Mistakes to Avoid

-   Jumping into coding without planning
-   Not clarifying requirements
-   Ignoring edge cases
-   Writing unclear/messy code
-   Not testing your solution

## 🌟 Success Tips

-   Think aloud while solving
-   Start with brute force, then optimize
-   Use meaningful variable names
-   Write clean, modular code
-   Test with edge cases

Ready to begin your journey to interview success? Let's dive into our first topic: Algorithmic Complexity and Big-O Notation! 🚀
# 🎯 Algorithmic Complexity & Big-O Guide

## 🎨 Visual Complexity Chart
Excellent  O(1) ▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁▁
Good      O(log n) ▁▁▁▁▂▂▂▂▂▂▂▂▂▂▂▂
Fair      O(n) ▁▁▁▂▂▂▃▃▃▄▄▄▅▅▅▆▆▆
Bad       O(n²) ▁▂▃▄▅▆▇█████████████
Horrible  O(2ⁿ) ▁▂▅█████████████████

![Big-O CheatSheet](https://i.postimg.cc/wjrdT9y3/temp-Image-Qsq7-Dm.avif)
[blog.algomaster.io](https://blog.algomaster.io/p/57bd4963-462f-4294-a972-4012691fc729)
## 🎮 What is Algorithmic Complexity?

Think of algorithmic complexity as your code's "price tag" in terms of:

-   ⏱️ Time (how long it takes to run)
-   💾 Space (how much memory it needs)

### 🎯 Why Should You Care?
````python
# Example 1: O(n) - Linear Time
def find_max_linear(arr):  # 😊 Good for small lists
    return max(arr)

# Example 2: O(n²) - Quadratic Time
def find_max_nested(arr):  # 😰 Terrible for large lists
    max_val = arr[0]
    for i in arr:
        for j in arr:  # Unnecessary nested loop!
            if i > max_val:
                max_val = i
    return max_val
````

## 🚀 Understanding Big-O Notation

### 📊 Common Time Complexities (From Best to Worst)

1.  **O(1) - Constant Time**  🌟
````python
def get_first(arr):
    return arr[0] if arr else None
````
-   Like finding a book when you know exactly where it is
-   Examples: Hash table access, array index access

2. **O(log n) - Logarithmic Time** ✨
````python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target: return mid
        if arr[mid] < target: left = mid + 1
        else: right = mid - 1
    return -1
````
 -   Like finding a word in a dictionary
-   Examples: Binary search, balanced BST operations
3. **O(n) - Linear Time** 👍
````python
def linear_search(arr, target):
    return any(x == target for x in arr)
````
-   Like reading every page in a book
-   Examples: Array traversal, linear search
4. **O(n log n) - Log-Linear Time** 🆗
````python
def merge_sort(arr):
    if len(arr) <= 1: return arr
    mid = len(arr) // 2
    return merge(merge_sort(arr[:mid]), 
                merge_sort(arr[mid:]))
````
-   Like sorting a deck of cards efficiently
-   Examples: Merge sort, quick sort (average case)
5. **O(n²) - Quadratic Time** 😰
````python
def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(len(arr) - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
````
-   Like comparing every page with every other page
-   Examples: Nested loops, bubble sort
6. **O(2ⁿ) - Exponential Time** 😱
````python
def fibonacci_recursive(n):
    if n <= 1: return n
    return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)
````
-   Like trying every possible combination
-   Examples: Recursive Fibonacci, power set
### 🎮 Common Space Complexities

1.  **O(1) - Constant Space**
    -   Fixed amount of extra space
    -   Example: Simple variables, fixed-size arrays
2.  **O(n) - Linear Space**
    -   Space grows linearly with input
    -   Example: Creating a new array of size n
3.  **O(n²) - Quadratic Space**
    -   Space grows quadratically
    -   Example: 2D array/matrix of size n×n
## 🎯 Big-O Cheat Sheet for Common Data Structures

### Array Operations
````python
# Access: O(1)
arr[5]  # Direct access by index

# Search: O(n)
target in arr  # Linear search

# Insertion/Deletion at end: O(1)
arr.append(item)  # Add to end
arr.pop()  # Remove from end

# Insertion/Deletion at middle: O(n)
arr.insert(2, item)  # Need to shift elements
````
### Dictionary/Hash Table Operations
````python
# Access/Insert/Delete: O(1) average
dict_example = {}
dict_example['key'] = 'value'  # O(1)
value = dict_example['key']    # O(1)
del dict_example['key']        # O(1)
````
## 🎮 Pro Tips for Optimization

1.  **Avoid Nested Loops When Possible**
````python
# Bad: O(n²)
for i in range(n):
    for j in range(n):
        # do something

# Better: O(n)
seen = set()
for i in range(n):
    if i in seen:
        # do something
````
2. **Use Built-in Data Structures Wisely**
````python
# Lists vs Sets for lookups
numbers = [1, 2, 3, 4, 5]
number_set = set(numbers)

# Bad: O(n)
5 in numbers

# Good: O(1)
5 in number_set
````
3. **Cache Results When Possible**
````python
from functools import lru_cache

@lru_cache(maxsize=None)
def fibonacci(n):
    if n < 2: return n
    return fibonacci(n-1) + fibonacci(n-2)
````
## 🎯 Practice Problems

1.  **Identify the Time Complexity**
````python
def mystery_function(n):
    result = 0
    for i in range(n):
        for j in range(i, n):
            result += 1
    return result

# What's the time complexity? 
# (Answer: O(n²))
````
Remember: The best algorithm is often a balance between:

-   ⏱️ Time complexity
-   💾 Space complexity
-   🎯 Code readability
-   🔧 Maintainability

# 🧮 Bit Manipulation & Sorting Algorithms
## Part 1: 🔢 Bit Manipulation

### 🎯 Why Bit Manipulation?

-   ⚡ More efficient than arithmetic operations
-   🚀 Essential for optimization problems
-   💻 Crucial for low-level programming
-   📝 Common in technical interviews

### 🛠️ Basic Operators
````python
# AND (&): 1 if both bits are 1
print(5 & 3)  # 5(101) & 3(011) = 1(001)

# OR (|): 1 if either bit is 1
print(5 | 3)  # 5(101) | 3(011) = 7(111)

# XOR (^): 1 if bits are different
print(5 ^ 3)  # 5(101) ^ 3(011) = 6(110)

# NOT (~): Inverts all bits
print(~5)     # 5(101) -> -(110)

# Left Shift (<<): Multiply by 2^n
print(5 << 1) # 5(101) << 1 = 10(1010)

# Right Shift (>>): Divide by 2^n
print(5 >> 1) # 5(101) >> 1 = 2(010)
````
### 🎮 Common Bit Manipulation Tricks

1.  **Check if Number is Even/Odd**
````python
def is_even(n: int) -> bool:
    return not (n & 1)  # Last bit is 0 for even numbers
````
2. **Multiply/Divide by Powers of 2**
````python
def multiply_by_2(n: int) -> int:
    return n << 1  # Left shift = multiply by 2

def divide_by_2(n: int) -> int:
    return n >> 1  # Right shift = divide by 2
````
3. **Set/Clear/Toggle Bits**
````python
def set_bit(n: int, pos: int) -> int:
    return n | (1 << pos)

def clear_bit(n: int, pos: int) -> int:
    return n & ~(1 << pos)

def toggle_bit(n: int, pos: int) -> int:
    return n ^ (1 << pos)
````
4. **Check if Bit is Set**
````python
def is_bit_set(n: int, pos: int) -> bool:
    return bool(n & (1 << pos))
````
### 🎯 Interview Tips for Bit Manipulation

1.  Always visualize bits on paper
2.  Test with small numbers first
3.  Consider edge cases (negatives, zero)
4.  Explain your logic step by step
## Part 2: 🔄 Sorting Algorithms

### 📊 Comparison Overview
````python
sorting_algos = {
    'Bubble Sort':    {'Time': 'O(n²)', 'Space': 'O(1)', 'Stable': True},
    'Selection Sort': {'Time': 'O(n²)', 'Space': 'O(1)', 'Stable': False},
    'Insertion Sort': {'Time': 'O(n²)', 'Space': 'O(1)', 'Stable': True},
    'Merge Sort':     {'Time': 'O(n log n)', 'Space': 'O(n)', 'Stable': True},
    'Quick Sort':     {'Time': 'O(n log n)', 'Space': 'O(log n)', 'Stable': False},
    'Heap Sort':      {'Time': 'O(n log n)', 'Space': 'O(1)', 'Stable': False}
}
````
### 🎯 Simple Sorting Algorithms

1.  **Bubble Sort**  (The Beginner's Sort)
````python
def bubble_sort(arr: list) -> list:
    n = len(arr)
    for i in range(n):
        # Flag for optimization
        swapped = False
        
        # Last i elements are already sorted
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        
        # If no swaps occurred, array is sorted
        if not swapped:
            break
    return arr

# When to use: Small arrays or nearly sorted data
# Pros: Simple to implement, in-place sorting
# Cons: Very inefficient for large datasets
````
2. **Selection Sort** (The Minimalist's Sort)
````python
def selection_sort(arr: list) -> list:
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

# When to use: Small arrays with expensive writes
# Pros: Minimum number of swaps
# Cons: Always makes O(n²) comparisons
````
3. **Insertion Sort** (The Adaptive Sort)
````python
def insertion_sort(arr: list) -> list:
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >= 0 and arr[j] > key:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr

# When to use: Small datasets or nearly sorted arrays
# Pros: Adaptive, stable, and great for small data
# Cons: Still O(n²) in worst case
````
### 🚀 Advanced Sorting Algorithms
1. **Merge Sort** (The Reliable Sort)
````python
def merge_sort(arr: list) -> list:
    if len(arr) <= 1:
        return arr
        
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    
    return merge(left, right)

def merge(left: list, right: list) -> list:
    result = []
    i = j = 0
    
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    
    result.extend(left[i:])
    result.extend(right[j:])
    return result

# When to use: Large datasets where stability matters
# Pros: Stable, predictable O(n log n)
# Cons: Requires O(n) extra space
````
2. **Quick Sort** (The Practical Sort)
````python
def quick_sort(arr: list) -> list:
    if len(arr) <= 1:
        return arr
    
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    
    return quick_sort(left) + middle + quick_sort(right)

# When to use: General-purpose sorting
# Pros: Usually fastest in practice
# Cons: Unstable, bad worst-case O(n²)
````
3. **Heap Sort** (The Memory-Efficient Sort)
````python
def heapify(arr: list, n: int, i: int):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[left] > arr[largest]:
        largest = left
    if right < n and arr[right] > arr[largest]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heap_sort(arr: list) -> list:
    n = len(arr)
    
    # Build max heap
    for i in range(n//2 - 1, -1, -1):
        heapify(arr, n, i)
    
    # Extract elements from heap
    for i in range(n-1, 0, -1):
        arr[0], arr[i] = arr[i], arr[0]
        heapify(arr, i, 0)
    
    return arr

# When to use: When space is a premium
# Pros: In-place, O(n log n) guaranteed
# Cons: Unstable, poor cache performance
````
### 🎨 Special Purpose Sorting Algorithms

1.  **Shell Sort**  (The Gap Sort)
````python
def shell_sort(arr: list) -> list:
    n = len(arr)
    gap = n // 2
    
    while gap > 0:
        for i in range(gap, n):
            temp = arr[i]
            j = i
            
            while j >= gap and arr[j-gap] > temp:
                arr[j] = arr[j-gap]
                j -= gap
            arr[j] = temp
        gap //= 2
    
    return arr

# When to use: Medium-sized arrays
# Pros: Adaptive, handles partially sorted arrays well
# Cons: Complex gap sequence selection
````
2. **Counting Sort** (The Integer Sort)
````python
def counting_sort(arr: list) -> list:
    if not arr:
        return arr
    
    # Find range of array elements
    max_val = max(arr)
    min_val = min(arr)
    range_val = max_val - min_val + 1
    
    # Create counting array and output array
    count = [0] * range_val
    output = [0] * len(arr)
    
    # Store count of each element
    for num in arr:
        count[num - min_val] += 1
    
    # Modify count array to store actual positions
    for i in range(1, len(count)):
        count[i] += count[i - 1]
    
    # Build output array
    for num in reversed(arr):
        output[count[num - min_val] - 1] = num
        count[num - min_val] -= 1
    
    return output

# When to use: Integer arrays with known range
# Pros: O(n) for known range integers
# Cons: Requires extra space proportional to range
````
3. **Radix Sort** (The Digit Sort)
````python
def counting_sort_for_radix(arr: list, exp: int) -> list:
    n = len(arr)
    output = [0] * n
    count = [0] * 10
    
    # Store count of occurrences
    for i in range(n):
        index = arr[i] // exp
        count[index % 10] += 1
    
    # Change count[i] to contain actual position
    for i in range(1, 10):
        count[i] += count[i - 1]
    
    # Build output array
    i = n - 1
    while i >= 0:
        index = arr[i] // exp
        output[count[index % 10] - 1] = arr[i]
        count[index % 10] -= 1
        i -= 1
    
    # Copy output array to arr
    for i in range(n):
        arr[i] = output[i]

def radix_sort(arr: list) -> list:
    if not arr:
        return arr
    
    # Find maximum number to know number of digits
    max_val = max(arr)
    
    # Do counting sort for every digit
    exp = 1
    while max_val // exp > 0:
        counting_sort_for_radix(arr, exp)
        exp *= 10
    
    return arr

# When to use: Integer arrays with fixed number of digits
# Pros: Linear time possible for fixed-length integers
# Cons: Only works with integers, uses extra space
````
4. **Bucket Sort** (The Distribution Sort)
````python
def bucket_sort(arr: list, num_buckets: int = 10) -> list:
    if not arr:
        return arr
    
    # Find range of values
    max_val, min_val = max(arr), min(arr)
    
    # Create buckets
    range_val = (max_val - min_val) / num_buckets
    buckets = [[] for _ in range(num_buckets)]
    
    # Put elements in buckets
    for num in arr:
        if num == max_val:
            bucket_idx = num_buckets - 1
        else:
            bucket_idx = int((num - min_val) / range_val)
        buckets[bucket_idx].append(num)
    
    # Sort individual buckets
    for bucket in buckets:
        bucket.sort()  # Using TimSort internally in Python
    
    # Concatenate all buckets into arr
    return [num for bucket in buckets for num in bucket]

# When to use: Uniformly distributed data over a range
# Pros: Linear time possible for uniform distribution
# Cons: Requires uniform distribution for efficiency
````
5. **Tim Sort** (Python's Built-in Sort)
````python
# Python's built-in sort uses TimSort
def tim_sort_example(arr: list) -> list:
    return sorted(arr)  # Uses TimSort internally

# When to use: General purpose sorting
# Pros: Excellent performance on real-world data
# Cons: Complex implementation, requires extra space
````
### 🎯 Best Practices for Each Algorithm

## Simple Sorts (O(n²))

-   **Bubble Sort**: Nearly sorted data, teaching purposes
-   **Selection Sort**: Small arrays, minimizing swaps
-   **Insertion Sort**: Small arrays, online sorting

## Efficient Sorts (O(n log n))

-   **Merge Sort**: Stable sorting needed, linked lists
-   **Quick Sort**: General purpose, arrays
-   **Heap Sort**: Memory constrained, guaranteed O(n log n)

## Special Purpose Sorts

-   **Shell Sort**: Medium-sized arrays, partially sorted data
-   **Counting Sort**: Small range integers
-   **Radix Sort**: Fixed-length integers, like phone numbers
-   **Bucket Sort**: Uniformly distributed floating-point numbers
-   **Tim Sort**: When you need the best of both worlds (stable & efficient)
### 🎮 Choosing the Right Sort

1.  **Consider Your Data**
    -   Size of dataset
    -   Data type (integers, floating-point, strings)
    -   Data distribution
    -   Range of values
2.  **Consider Your Constraints**
    -   Memory limitations
    -   Stability requirements
    -   Whether data is streaming (online)
    -   Performance requirements
3.  **General Guidelines**
    -   Small dataset (n < 50): Insertion Sort
    -   Memory constrained: Heap Sort
    -   Stability required: Merge Sort
    -   General purpose: Quick Sort or Tim Sort
    -   Integer data: Counting Sort or Radix Sort

Remember: In Python, use the built-in  `sort()`  or  `sorted()`  for best performance! They use TimSort, which is optimized for real-world data patterns. 🚀
# 🔗 Linked Lists & Dummy Node Technique Guide

## 📘 Understanding Linked Lists

### 🎯 What is a Linked List?
````python
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
````
### 📊 Types of Linked Lists

1.  **Singly Linked List**
````python
# 1 -> 2 -> 3 -> None
head = ListNode(1)
head.next = ListNode(2)
head.next.next = ListNode(3)
````
2. **Doubly Linked List**
````python
class DoublyListNode:
    def __init__(self, val=0, next=None, prev=None):
        self.val = val
        self.next = next
        self.prev = prev
````
3. **Circular Linked List**
````python
# 1 -> 2 -> 3 -> 1 (cycles back)
head = ListNode(1)
head.next = ListNode(2)
head.next.next = ListNode(3)
head.next.next.next = head  # Creates cycle
````

## 📚 Core Implementation Options

### 1️⃣ Using collections.deque
````python
from collections import deque

# Creating linked lists
llist = deque()              # Empty list
llist = deque([1, 2, 3])     # From iterable
llist = deque('abc')         # From string

# Common Operations
llist.append(x)      # Add to right
llist.appendleft(x)  # Add to left
llist.pop()          # Remove from right
llist.popleft()      # Remove from left
````

### 2️⃣ Custom Linked List Implementation
````python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
    
    def __repr__(self):
        return str(self.data)

class LinkedList:
    def __init__(self, nodes=None):
        self.head = None
        if nodes:
            node = Node(data=nodes.pop(0))
            self.head = node
            for elem in nodes:
                node.next = Node(data=elem)
                node = node.next
    
    def __repr__(self):
        nodes = []
        curr = self.head
        while curr:
            nodes.append(str(curr.data))
            curr = curr.next
        return " -> ".join(nodes + ["None"])
    
    def __iter__(self):
        node = self.head
        while node:
            yield node
            node = node.next
````
## 🎯 Common Pattern Templates

### 1️⃣ Two-Pointer Technique Template
````python
def two_pointer_template(head):
    # Initialize pointers
    slow = fast = head
    
    # Move pointers
    while fast and fast.next:
        slow = slow.next           # Move one step
        fast = fast.next.next      # Move two steps
        
        # Optional: Detection logic here
        if slow == fast:
            return True  # Or other logic
    
    return False
````
### 2️⃣ Reverse List Template
````python
def reverse_template(head):
    prev = None
    current = head
    
    while current:
        # Store next
        next_node = current.next
        # Reverse pointer
        current.next = prev
        # Move prev and current
        prev = current
        current = next_node
    
    return prev  # New head
````
### 3️⃣ Merge Lists Template
````python
def merge_template(l1, l2):
    dummy = Node(0)
    current = dummy
    
    while l1 and l2:
        if l1.val <= l2.val:
            current.next = l1
            l1 = l1.next
        else:
            current.next = l2
            l2 = l2.next
        current = current.next
    
    # Attach remaining nodes
    current.next = l1 or l2
    return dummy.next
````
## 🛠️ Essential Operations Templates

### 1️⃣ Node Insertion
````python
def insert_operations():
    # Insert at beginning - O(1)
    def add_first(self, node):
        node.next = self.head
        self.head = node
    
    # Insert at end - O(n)
    def add_last(self, node):
        if not self.head:
            self.head = node
            return
        for current in self:
            pass
        current.next = node
    
    # Insert after node - O(n)
    def add_after(self, target_data, new_node):
        if not self.head:
            raise Exception("List is empty")
            
        for node in self:
            if node.data == target_data:
                new_node.next = node.next
                node.next = new_node
                return
                
        raise Exception("Node not found")
````
### 2️⃣ Node Deletion
````python
def removal_template(self, target):
    if not self.head:
        raise Exception("List is empty")
    
    # Handle head removal
    if self.head.data == target:
        self.head = self.head.next
        return
    
    # Handle other removals
    current = self.head
    while current.next:
        if current.next.data == target:
            current.next = current.next.next
            return
        current = current.next
    
    raise Exception("Node not found")
````

## 🎯 The Dummy Node Technique

### 🔑 Why Use Dummy Nodes?

1.  Simplifies edge cases
2.  Avoids null pointer exceptions
3.  Makes code cleaner and more uniform
4.  Particularly useful for:
    -   List manipulation
    -   Merging lists
    -   Removing elements
    -   Complex operations

### 📝 Dummy Node Pattern Template
````python
def linked_list_operation(head: ListNode) -> ListNode:
    # Create dummy node
    dummy = ListNode(0)
    dummy.next = head
    
    # Work with dummy node
    current = dummy
    while current.next:
        # Perform operations
        current = current.next
    
    # Return modified list
    return dummy.next
````
### 🎯 Advanced Techniques with Dummy Nodes

1.  **Multiple Dummy Nodes**
````python
def oddEvenList(head: ListNode) -> ListNode:
    if not head:
        return None
        
    # Two dummy nodes for odd and even lists
    odd_dummy = ListNode(0)
    even_dummy = ListNode(0)
    odd = odd_dummy
    even = even_dummy
    
    is_odd = True
    current = head
    
    while current:
        if is_odd:
            odd.next = current
            odd = odd.next
        else:
            even.next = current
            even = even.next
        is_odd = not is_odd
        current = current.next
    
    # Connect odd and even lists
    odd.next = even_dummy.next
    even.next = None
    return odd_dummy.next
````
2. **Dummy Node w/ Fast/Slower Pointers**
````python
def hasCycle(head: ListNode) -> bool:
    dummy = ListNode(0)
    dummy.next = head
    slow = dummy
    fast = dummy
    
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
            
    return False
````
### 🎯 Interview Tips

1.  **When to Use Dummy Nodes**
    -   List modification required
    -   Head might change
    -   Multiple pointer manipulation
    -   Merging or splitting lists
2.  **Common Patterns**
````python
# Pattern 1: Basic Dummy Node
dummy = ListNode(0)
dummy.next = head
current = dummy

# Pattern 2: Multiple Pointers
dummy = ListNode(0)
slow = fast = dummy

# Pattern 3: Multiple Dummies
dummy1 = ListNode(0)
dummy2 = ListNode(0)
````
1.  **Edge Cases to Consider**
    -   Empty list
    -   Single node
    -   Two nodes
    -   Cycles in list
    -   Duplicate values

### 🎮 Practice Problems

1.  Reverse Linked List
2.  Detect Cycle
3.  Find Middle Node
4.  Remove Duplicates
5.  Merge K Sorted Lists

Remember:

-   Always handle edge cases first
-   Consider using dummy nodes for cleaner code
-   Test with small examples
-   Draw the list operations on paper
-   Keep track of all pointers carefully

# 🔄 Stack & Queue Implementations in Python

## 📚 Stack Implementations

### 1️⃣ Using List as Stack
````python
class ListStack:
    def __init__(self):
        self.stack = []
    
    def push(self, item):
        self.stack.append(item)
    
    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        raise IndexError("Stack is empty")
    
    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        raise IndexError("Stack is empty")
    
    def is_empty(self):
        return len(self.stack) == 0
    
    def size(self):
        return len(self.stack)
````
### 2️⃣ Using Collections.deque as Stack
````python
from collections import deque

class DequeStack:
    def __init__(self):
        self.stack = deque()
    
    def push(self, item):
        self.stack.append(item)
    
    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        raise IndexError("Stack is empty")
    
    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        raise IndexError("Stack is empty")
    
    def is_empty(self):
        return len(self.stack) == 0
    
    def size(self):
        return len(self.stack)
````
### Common Stack Pattern Templates

1.  **Basic Stack Operations Pattern**
````python
def stack_pattern(data):
    stack = []  # or deque()
    
    for item in data:
        # Process current item
        while stack and some_condition(stack[-1], item):
            # Do something with stack.pop()
            pass
        stack.append(item)
    
    return result
````
2. **Monotonic Stack Pattern**
````python
def monotonic_stack_pattern(arr):
    stack = []  # stores indices usually
    result = [0] * len(arr)  # or any default value
    
    for i in range(len(arr)):
        # For increasing stack (next smaller)
        while stack and arr[stack[-1]] > arr[i]:
            popped = stack.pop()
            result[popped] = i - popped  # or any calculation
        stack.append(i)
    
    return result
````
## 📝 Queue Implementations

### 1️⃣ Using Collections.deque as Queue
````python
from collections import deque

class DequeQueue:
    def __init__(self):
        self.queue = deque()
    
    def enqueue(self, item):
        self.queue.append(item)
    
    def dequeue(self):
        if not self.is_empty():
            return self.queue.popleft()
        raise IndexError("Queue is empty")
    
    def front(self):
        if not self.is_empty():
            return self.queue[0]
        raise IndexError("Queue is empty")
    
    def rear(self):
        if not self.is_empty():
            return self.queue[-1]
        raise IndexError("Queue is empty")
    
    def is_empty(self):
        return len(self.queue) == 0
    
    def size(self):
        return len(self.queue)
````
### 2️⃣ Queue Implementation
````python
from queue import Queue

# Thread-safe queue usage
queue = Queue()
queue.put(item)      # Enqueue
item = queue.get()   # Dequeue
size = queue.qsize() # Size
empty = queue.empty()
````

## 🎯 Common Implementation Patterns

### Pattern 1: LIFO Stack Pattern
````python
def stack_pattern(data):
    stack = []  # or deque()
    
    for item in data:
        # Process current item
        while stack and condition(stack[-1], item):
            # Process stack.pop()
            pass
        stack.append(item)
    
    return result
````
### Pattern 2: FIFO Queue Pattern
````python
def queue_pattern(start_node):
    queue = deque([start_node])
    seen = {start_node}
    
    while queue:
        current = queue.popleft()
        # Process current node
        
        for neighbor in get_neighbors(current):
            if neighbor not in seen:
                seen.add(neighbor)
                queue.append(neighbor)
````

## 🔑 Key Operations & Complexities

### Stack Operations
````python
operations = {
    'push':    'O(1)',  # Add to top
    'pop':     'O(1)',  # Remove from top
    'peek':    'O(1)',  # View top element
    'isEmpty': 'O(1)',  # Check if empty
    'size':    'O(1)'   # Get number of elements
}
````
### Queue Operations
````python
operations = {
    'enqueue': 'O(1)',  # Add to back
    'dequeue': 'O(1)',  # Remove from front
    'front':   'O(1)',  # View front element
    'isEmpty': 'O(1)',  # Check if empty
    'size':    'O(1)'   # Get number of elements
}
````
## 💡When to Use What

### Use Stack When:

-   Need LIFO (Last In, First Out) behavior
-   Tracking state changes (undo/redo)
-   Parse expressions (parentheses matching)
-   Function call management
-   DFS implementation

### Use Queue When:

-   Need FIFO (First In, First Out) behavior
-   Order must be preserved
-   BFS implementation
-   Task scheduling
-   Resource pooling


## 🎯 Implementation Comparison

### Stack Implementation Comparison
````
# List as Stack
- Pros: Simple, built-in, good for small data
- Cons: Potential memory reallocation for large data
- Use when: Simple stack operations needed

# Deque as Stack
- Pros: Efficient memory usage, thread-safe
- Cons: Slightly more complex than list
- Use when: Large data or thread safety needed
````
### Queue Implementation Comparison
````
# Deque as Queue
- Pros: O(1) operations, efficient memory
- Cons: Not fixed size
- Use when: General queue operations needed

# Queue
- Pros: Memory efficient, fixed size
- Cons: More complex implementation
- Use when: Fixed size buffer needed
````

## 🎮 Practice Problem Tips

1.  Always clarify:
    -   Is there a size limit?
    -   What happens on empty pop/dequeue?
    -   Should operations be thread-safe?
    -   What type of elements to store?
2.  Consider:
    -   Time/Space complexity requirements
    -   Concurrency needs
    -   Error handling approach
    -   Edge cases

Remember:

-   Use  `collections.deque`  for efficient implementation
-   Consider thread-safety needs before choosing implementation
-   Watch for operation order dependence
-   Handle edge cases explicitly

# 🗃️ Hash Tables in Python (Dictionaries)

## 📚 Basic Implementation

### 1️⃣ Dictionary Creation
````python
# Method 1: Using curly braces
hash_map = {
    'key1': 'value1',
    'key2': 'value2'
}

# Method 2: Using dict() constructor
hash_map = dict(
    key1='value1',
    key2='value2'
)

# Method 3: From list of tuples
hash_map = dict([
    ('key1', 'value1'),
    ('key2', 'value2')
])

# Method 4: Empty dictionary
hash_map = {}
````
### 2️⃣ Basic Operations
````python
# Access Operations - O(1) average case
hash_map['key'] = 'value'  # Insert/Update
value = hash_map['key']    # Access
del hash_map['key']        # Delete

# Safe Access
value = hash_map.get('key', default_value)  # Returns default_value if key not found

# Check Existence - O(1)
if 'key' in hash_map:
    # Key exists
    pass
````

## 🎯 Common Hash Table Patterns

### 1️⃣ Counting Pattern
````python
def counting_pattern(items):
    counter = {}
    
    # Count occurrences
    for item in items:
        counter[item] = counter.get(item, 0) + 1
    
    return counter

# Alternative using defaultdict
from collections import defaultdict

def counting_with_defaultdict(items):
    counter = defaultdict(int)
    for item in items:
        counter[item] += 1
    return counter
````
### 2️⃣ Grouping Pattern
````python
def grouping_pattern(items, key_func):
    groups = {}
    
    for item in items:
        key = key_func(item)
        if key not in groups:
            groups[key] = []
        groups[key].append(item)
    
    return groups

# Alternative using defaultdict
def grouping_with_defaultdict(items, key_func):
    groups = defaultdict(list)
    for item in items:
        groups[key_func(item)].append(item)
    return groups
````
### 3️⃣ Caching/Memoization Pattern
````python
def memoization_pattern():
    cache = {}
    
    def memoized_func(arg):
        if arg not in cache:
            cache[arg] = compute_value(arg)
        return cache[arg]
    
    return memoized_func

# Alternative using @lru_cache
from functools import lru_cache

@lru_cache(maxsize=None)
def cached_function(arg):
    return compute_value(arg)
````
### 4️⃣ Two-Sum Pattern
````python
def two_sum_pattern(nums, target):
    seen = {}  # value -> index
    
    for i, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], i]
        seen[num] = i
    
    return []
````
## 🎮 Advanced Techniques

### 1️⃣ Multi-Level Dictionary
````python
# Creation
multi_level = {
    'level1': {
        'level2': {
            'level3': 'value'
        }
    }
}

# Safe Navigation
def safe_get(dictionary, *keys, default=None):
    current = dictionary
    for key in keys:
        if not isinstance(current, dict):
            return default
        current = current.get(key, default)
    return current
````
### 2️⃣ Dictionary Comprehension
````python
# Basic comprehension
squares = {x: x*x for x in range(5)}

# Conditional comprehension
even_squares = {x: x*x for x in range(5) if x % 2 == 0}

# Transforming dictionaries
transformed = {k: v*2 for k, v in original.items()}
````
### 3️⃣ Advanced Operations
````python
# Merging dictionaries
dict3 = {**dict1, **dict2}  # Python 3.5+
dict3 = dict1 | dict2       # Python 3.9+

# Get multiple values safely
values = [hash_map.get(key) for key in keys]

# Delete multiple keys
for key in keys_to_delete:
    hash_map.pop(key, None)  # Won't raise KeyError
````

## 📝 Common Interview Problem Patterns

1.  **Frequency Counter Problems**
    -   Character frequency in strings
    -   Word frequency in sentences
    -   Element frequency in arrays
2.  **Two-Sum Type Problems**
    -   Finding pairs with target sum
    -   Finding triplets
    -   Subarray with given sum
3.  **Caching Problems**
    -   Implementing LRU cache
    -   Memoization problems
    -   Function results caching
4.  **String Problems**
    -   Anagram detection
    -   First non-repeating character
    -   String permutations

## 🎯 Practice Problems

1.  **Frequency Based**
    -   Find the first non-repeating character in a string
    -   Find if two strings are anagrams
    -   Most frequent element in an array
2.  **Lookup Based**
    -   Implement two sum
    -   Group anagrams together
    -   Find all pairs with given difference
3.  **Caching Based**
    -   Implement LRU cache
    -   Design a file system cache
    -   Implement memoization decorator
4.  **Advanced Problems**
    -   Design a time-based key-value store
    -   Implement a data structure that supports insert, delete, getRandom in O(1)
    -   Design a logger rate limiter

## ⚠️ Common Pitfalls to Watch For

1.  **Mutability Issues**
    -   Using mutable objects as dictionary keys
    -   Modifying dictionary while iterating
2.  **Performance Traps**
    -   Repeatedly accessing the same key
    -   Not using .get() for default values
    -   Unnecessary key existence checks
3.  **Memory Issues**
    -   Unbounded growth in caching problems
    -   Not clearing references in long-running applications
4.  **Edge Cases**
    -   Empty dictionaries
    -   Non-existent keys
    -   None values vs missing keys

Remember: Hash tables provide O(1) average case operations but require good hash functions and collision handling strategies. In Python, this is handled automatically by the dictionary implementation.

# 🌳 Heaps for Technical Interviews

## 📚 Core Concepts

### What is a Heap?
````python
"""
A heap is a complete binary tree that satisfies the heap property:
- Max Heap: Parent nodes are greater than or equal to children
- Min Heap: Parent nodes are less than or equal to children
- Python's heapq implements min heap
"""

# Key Properties:
properties = {
    "Complete Binary Tree": "All levels filled except possibly last level",
    "Heap Property": "Parent-child relationship maintained throughout",
    "Root": "Smallest element (min heap) or largest element (max heap)",
    "Implementation": "Usually backed by an array/list",
    "Height": "O(log n) where n is number of nodes"
}
````
### Parent-Child Relationships in Array Implementation
````python
def get_relationships(i: int) -> dict:
    return {
        'parent': (i - 1) // 2,    # Parent index
        'left_child': 2 * i + 1,   # Left child index
        'right_child': 2 * i + 2,  # Right child index
    }    
````
## 🔧 Basic Operations Using heapq

### 1. Heap Creation
````python
import heapq

# Method 1: Heapify existing list
numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
heapq.heapify(numbers)  # O(n)

# Method 2: Create empty heap (just use list)
heap = []
````
### 2. Core Operations
````python
def heap_operations():
    heap = []
    
    # Push - O(log n)
    heapq.heappush(heap, 5)
    
    # Pop - O(log n)
    smallest = heapq.heappop(heap)
    
    # Peek - O(1)
    if heap:
        smallest = heap[0]
    
    # Push and Pop combined - O(log n)
    smallest = heapq.heappushpop(heap, 4)  # Push then pop
    smallest = heapq.heapreplace(heap, 4)  # Pop then push
````
### 3. Helper Functions
````python
def heap_helpers(items):
    # Find n smallest elements - O(n log k)
    n_smallest = heapq.nsmallest(3, items)
    
    # Find n largest elements - O(n log k)
    n_largest = heapq.nlargest(3, items)
    
    # Merge sorted iterables - O(n log k)
    merged = heapq.merge([1,3,5], [2,4,6])
````
## 🎯 Common Heap Patterns

### 1. Priority Queue Implementation
````python
from dataclasses import dataclass, field
from typing import Any

@dataclass(order=True)
class PrioritizedItem:
    priority: int
    item: Any = field(compare=False)

class PriorityQueue:
    def __init__(self):
        self._queue = []
    
    def push(self, item, priority):
        heapq.heappush(self._queue, PrioritizedItem(priority, item))
    
    def pop(self):
        return heapq.heappop(self._queue).item
    
    def peek(self):
        return self._queue[0].item if self._queue else None
````
### 2. K-Way Merge Pattern
````python
def k_way_merge(sorted_arrays):
    """Merge k sorted arrays using heap."""
    merged = []
    heap = []
    
    # Initialize heap with first element from each array
    for i, arr in enumerate(sorted_arrays):
        if arr:
            heapq.heappush(heap, (arr[0], i, 0))
    
    while heap:
        val, array_index, elem_index = heapq.heappop(heap)
        merged.append(val)
        
        if elem_index + 1 < len(sorted_arrays[array_index]):
            next_val = sorted_arrays[array_index][elem_index + 1]
            heapq.heappush(heap, (next_val, array_index, elem_index + 1))
    
    return merged
````
### 3. Running Median Pattern
````python
class MedianFinder:
    def __init__(self):
        self.small = []  # max heap (-ve numbers)
        self.large = []  # min heap

    def add_num(self, num: int) -> None:
        # Add to appropriate heap
        if len(self.small) == len(self.large):
            heapq.heappush(self.large, -heapq.heappushpop(self.small, -num))
        else:
            heapq.heappush(self.small, -heapq.heappushpop(self.large, num))

    def find_median(self) -> float:
        if len(self.small) == len(self.large):
            return (-self.small[0] + self.large[0]) / 2.0
        return float(self.large[0])
````
## 🎯 Common Interview Problems

### Problem Types

1.  K-th Element Problems
````python
def find_kth_largest(nums: List[int], k: int) -> int:
    heap = []
    for num in nums:
        heapq.heappush(heap, num)
        if len(heap) > k:
            heapq.heappop(heap)
    return heap[0]
````
2. Merge Problems
````python
def merge_k_arrays(arrays: List[List[int]]) -> List[int]:
    return list(heapq.merge(*arrays))
````
3. Scheduling Problems
````python
def min_meeting_rooms(intervals: List[List[int]]) -> int:
    heap = []  # Track end times
    for start, end in sorted(intervals):
        if heap and heap[0] <= start:
            heapq.heapreplace(heap, end)
        else:
            heapq.heappush(heap, end)
    return len(heap)    
````
### ⚠️ Edge Cases to Consider
````python
def edge_cases_to_check():
    """
    1. Empty heap operations
    2. Single element heap
    3. Duplicate elements
    4. Negative numbers
    5. Very large numbers
    6. Equal priorities in priority queue
    """
    pass
````
### 🎯 Time Complexity Summary
````python
complexities = {
    "heapify": "O(n)",
    "push": "O(log n)",
    "pop": "O(log n)",
    "peek": "O(1)",
    "heappushpop": "O(log n)",
    "nlargest/nsmallest": "O(n log k)",  # where k is the count requested
    "merge k sorted lists": "O(n log k)"  # where k is number of lists
}
````
## 💡 Interview Tips

1.  Use heap when:
    -   Need to find k largest/smallest elements
    -   Need to continuously find min/max
    -   Need to merge sorted sequences
    -   Implementing priority queue
2.  Python Heap Notes:
    -   heapq implements min heap
    -   For max heap, negate values
    -   No decrease-key operation
    -   Can't access arbitrary elements
3.  Solution Strategy:
    -   Identify if problem needs min or max heap
    -   Consider if heap is overkill (sorted list might work)
    -   Check if priority queue would be clearer
    -   Think about space complexity tradeoffs

Remember:

-   Always verify time/space complexity
-   Consider edge cases
-   Explain heap property while coding
-   Mention alternative approaches
# 🔄 Recursion Guide for Technical Interviews

## 📚 Core Concepts

### What is Recursion?
````python
"""
Recursion is when a function calls itself either:
1. Directly: The function directly calls itself
2. Indirectly: Function A calls Function B which calls Function A

Key Components:
1. Base Case (stopping condition)
2. Recursive Case (moving towards base case)
"""
````
### Key Elements of Recursive Function
````python
def recursive_function(input):
    # 1. Base Case
    if input <= base_case:
        return base_value
        
    # 2. Recursive Case
    # - Must move towards base case
    # - Usually operates on smaller input
    return recursive_function(smaller_input)
````
## 🎯 Common Recursion Patterns

### 1. Linear Recursion Pattern
````python
def linear_recursion(n: int) -> int:
    # Base case
    if n <= 0:
        return base_value
        
    # Single recursive call
    return recursive_step(linear_recursion(n - 1))

# Example: Factorial
def factorial(n: int) -> int:
    if n <= 1:  # Base case
        return 1
    return n * factorial(n - 1)  # Recursive case
````
### 2. Binary Recursion Pattern
````python
def binary_recursion(data):
    # Base case
    if base_condition(data):
        return base_value
        
    # Two recursive calls
    left = binary_recursion(left_portion(data))
    right = binary_recursion(right_portion(data))
    return combine(left, right)

# Example: Binary Tree Traversal
def traverse(root):
    if not root:
        return
    traverse(root.left)
    traverse(root.right)
````
### 3. Tail Recursion Pattern
````python
def tail_recursion(n, accumulator=initial_value):
    # Base case
    if n <= 0:
        return accumulator
        
    # Recursive call must be last operation
    return tail_recursion(n - 1, next_accumulator)

# Example: Tail Recursive Factorial
def factorial_tail(n: int, acc: int = 1) -> int:
    if n <= 1:
        return acc
    return factorial_tail(n - 1, n * acc)
````
### 4. Nested Recursion Pattern
````python
def nested_recursion(n):
    # Base case
    if n <= 0:
        return base_value
        
    # Recursive call within recursive call
    return nested_recursion(nested_recursion(n - 1))
````
## 📝 Common Interview Problem Types

### 1. Tree/Graph Problems
````python
def tree_traversal(root):
    # Base case
    if not root:
        return
        
    # Process current node
    process(root)
    
    # Recurse on children
    for child in root.children:
        tree_traversal(child)
````
### 2. String/Array Problems
````python
def is_palindrome(s: str) -> bool:
    # Base case: empty string or single char
    if len(s) <= 1:
        return True
        
    # Check outermost chars and recurse on inner
    return s[0] == s[-1] and is_palindrome(s[1:-1])
````
### 3. Divide and Conquer Problems
````python
def quick_sort(arr: list) -> list:
    # Base case
    if len(arr) <= 1:
        return arr
        
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    
    # Recursive case
    return quick_sort(left) + middle + quick_sort(right)
````
## ⚠️ Common Pitfalls & Solutions

### 1. Stack Overflow
````python
from sys import setrecursionlimit

def handle_deep_recursion(n: int):
    # Increase recursion limit if needed
    setrecursionlimit(10000)  # Default is 1000
    
    # Or better: Convert to iteration
    def iterative_version():
        stack = []
        while stack:
            # Process iteratively
            pass
````
### 2. Redundant Computations
````python
def fibonacci_with_memo(n: int, memo: dict = None) -> int:
    if memo is None:
        memo = {}
    
    # Check memo before computing
    if n in memo:
        return memo[n]
        
    # Base cases
    if n <= 1:
        return n
        
    # Store result in memo
    memo[n] = fibonacci_with_memo(n-1, memo) + fibonacci_with_memo(n-2, memo)
    return memo[n]
````
### 3. Not Moving Towards Base Case
````python
def ensure_progress(n: int) -> int:
    # Bad: Might never reach base case
    if n != 0:
        return ensure_progress(n)
    
    # Good: Always moves towards base case
    if n <= 0:
        return 0
    return ensure_progress(n - 1)
````
## 🎯 Time/Space Complexity Analysis

### Time Complexity Patterns
````python
complexities = {
    "Linear Recursion": "O(n) - Each call reduces n by 1",
    "Binary Recursion": "O(2^n) - Each call spawns 2 more calls",
    "Divide & Conquer": "O(n log n) - Divides problem in half each time",
    "Tail Recursion": "O(n) - Can be optimized by compiler",
}
````
### Space Complexity Considerations
````python
space_usage = {
    "Call Stack": "Each recursive call adds a frame",
    "Linear Recursion": "O(n) stack space",
    "Tail Recursion": "O(1) with optimization",
    "Tree Recursion": "O(h) where h is tree height"
}
````
## 💡 Interview Tips

1.  Always start with:
    -   Base case identification
    -   How to move towards base case
    -   Whether recursion makes sense
2.  Consider converting to iteration if:
    -   Deep recursion possible
    -   Space complexity is crucial
    -   Performance is critical
3.  Optimize using:
    -   Memoization for overlapping subproblems
    -   Tail recursion when possible
    -   Helper functions for additional parameters
4.  Be prepared to explain:
    -   Why recursion is appropriate
    -   Space/time complexity
    -   How to handle edge cases

Remember:

-   Clarity over cleverness
-   Consider both recursive and iterative solutions
-   Watch for stack overflow in large inputs
-   Test with small examples first

# ♻️ Backtracking Guide 
## 📚 Core Properties

### 1️⃣ Property 1: No Repetition and Completion
````python
"""
Backtracking is a systematic method that:
1. Avoids repetitions
2. Doesn't miss any possible solutions
3. Builds solutions incrementally
4. Returns to previous states ("backtracks")

Ideal for:
- Combinatorial problems (permutations, combinations)
- Enumeration problems
- Path finding in graphs
"""
````
### 2️⃣ Property 2: Search Pruning
````python
"""
During solution building:
1. Evaluates partial solutions
2. Prunes branches that can't lead to valid solutions
3. Skips invalid configurations
4. Abandons paths worse than known solutions

Ideal for:
- Constraint satisfaction problems (CSP)
- Optimization problems
- Game-playing scenarios
"""
````
## 🎯 Implementation Patterns

### 1. Two-Pass Pattern
````python
def backtrack_pattern(input_data):
    def dfs(curr_state):
        # Forward Pass: Build solution incrementally
        for choice in get_valid_choices(curr_state):
            # 1. Make choice
            apply_choice(curr_state, choice)
            
            # 2. Recurse
            dfs(curr_state)
            
            # Backward Pass: Reset state
            undo_choice(curr_state, choice)
    
    initial_state = create_initial_state()
    dfs(initial_state)
````
### Best Used When:

1.  **State Modification Required**
````python
# Example: N-Queens Problem
def solve_n_queens(n):
    def dfs(board, row):
        # Forward: Place queen
        board[row][col] = 'Q'
        solve_further(board, row + 1)
        # Backward: Remove queen
        board[row][col] = '.'
````
2. **Grid/Matrix Problems**
````python
# Example: Maze Solving
def solve_maze(maze):
    def dfs(x, y):
        # Forward: Mark path
        maze[x][y] = 'PATH'
        explore_neighbors(x, y)
        # Backward: Unmark if dead end
        maze[x][y] = 'EMPTY'
````
3. **Graph Problems with State Changes**
````python
# Example: Graph Coloring
def color_graph(graph):
    def dfs(node, colors):
        # Forward: Color node
        node.color = next_color
        color_neighbors(node)
        # Backward: Reset if invalid
        node.color = None
````
### Characteristics:

-   Need to maintain and restore state
-   Solutions built by modifying shared state
-   Requires explicit cleanup
-   Common in problems with global constraints


### 2. State Tracking Pattern
````python
def state_tracking_pattern():
    used = set()  # or list/array for tracking used elements
    curr = []     # current partial solution
    
    def dfs(state):
        if is_complete(state):
            record_solution(curr[:])
            return
            
        for choice in get_choices(state):
            if choice not in used:
                # Forward pass
                used.add(choice)
                curr.append(choice)
                
                dfs(next_state(state, choice))
                
                # Backward pass
                used.remove(choice)
                curr.pop()
````

### Best Used When:

1.  **Building Combinations/Permutations**
````python
# Example: Generate Subsets
def subsets(nums):
    result = []
    curr = []
    def dfs(start):
        result.append(curr[:])
        for i in range(start, len(nums)):
            curr.append(nums[i])
            dfs(i + 1)
            curr.pop()
````
2. **Building Sequences**
````python
# Example: Phone Number Letter Combinations
def letter_combinations(digits):
    curr = []
    def dfs(index):
        if len(curr) == len(digits):
            result.append(''.join(curr))
            return
        for letter in mapping[digits[index]]:
            curr.append(letter)
            dfs(index + 1)
            curr.pop()
````
3. **Path Finding Without State Modification**
````python
# Example: All Paths from Source to Target
def all_paths(graph):
    curr_path = []
    def dfs(node):
        curr_path.append(node)
        dfs(next_node)
        curr_path.pop()
````
### Characteristics:

-   Solutions built by tracking sequences
-   No need for explicit state restoration
-   Usually involves collecting multiple solutions
-   Common in combinatorial problems

## 🎯 Decision Making Guide

### Use Two-Pass Pattern When:

1.  Working with:
    -   Board games (Chess, N-Queens)
    -   Maze problems
    -   Grid-based problems
    -   Graph coloring
    -   State modification required
2.  Need to:
    -   Modify and restore shared state
    -   Handle complex constraints
    -   Work with matrix/grid structures
    -   Deal with global state

### Use State Tracking Pattern When:

1.  Working with:
    -   Combinations/Permutations
    -   String building problems
    -   Subset generation
    -   Path finding without modification
    -   Sequence generation
2.  Need to:
    -   Build multiple solutions
    -   Generate all possible arrangements
    -   Work with independent states
    -   Create combinations or selections

## 🎮 Hybrid Approach Examples

Sometimes you might need to combine both patterns:
````python
def hybrid_backtracking():
    curr_path = []  # State Tracking
    board = [[0] * N for _ in range(N)]  # Two-Pass State
    
    def dfs(row, col):
        # State Tracking: Build path
        curr_path.append((row, col))
        
        # Two-Pass: Modify board
        board[row][col] = 'VISITED'
        
        # Recurse
        explore_neighbors(row, col)
        
        # Two-Pass: Restore board
        board[row][col] = 'EMPTY'
        
        # State Tracking: Remove from path
        curr_path.pop()
````
### When to Use Hybrid:

1.  Complex game scenarios
2.  Path finding with state constraints
3.  Problems requiring both solution building and state modification
4.  Problems with both global and local constraints

Remember:

-   Consider state management needs
-   Think about solution collection requirements
-   Evaluate constraint checking needs
-   Consider readability and maintainability


## 🎮 Common Problem Types

### 1. Permutation Problems
````python
def permute(nums: List[int]) -> List[List[int]]:
    def backtrack(curr: List[int], used: Set[int]):
        # Base case: complete permutation
        if len(curr) == len(nums):
            result.append(curr[:])
            return
        
        # Try each unused number
        for i in range(len(nums)):
            # Skip used numbers
            if i in used:
                continue
            
            # Forward pass
            used.add(i)
            curr.append(nums[i])
            
            backtrack(curr, used)
            
            # Backward pass
            used.remove(i)
            curr.pop()
    
    result = []
    backtrack([], set())
    return result
````
### 2. Unique Permutations (With Duplicates)
````python
def permuteUnique(nums: List[int]) -> List[List[int]]:
    def backtrack(curr: List[int], counter: Dict[int, int]):
        if len(curr) == len(nums):
            result.append(curr[:])
            return
        
        # Use counter to handle duplicates
        for num in counter:
            if counter[num] > 0:
                curr.append(num)
                counter[num] -= 1
                
                backtrack(curr, counter)
                
                curr.pop()
                counter[num] += 1
    
    result = []
    counter = Counter(nums)
    backtrack([], counter)
    return result
````
### 3. Constraint Satisfaction Problems
````python
def solve_csp(constraints):
    def is_valid_state(state):
        return all(constraint(state) for constraint in constraints)
    
    def backtrack(state):
        if is_complete(state):
            return is_valid_state(state)
        
        for value in get_possible_values(state):
            if is_valid_partial(state, value):
                apply_value(state, value)
                
                if backtrack(state):
                    return True
                    
                undo_value(state, value)
        
        return False
````
## 🎯 Time Complexity Analysis
````python
complexity_notes = {
    "Permutations": {
        "Time": "O(n!)",
        "Space": "O(n) for recursion stack",
        "Note": "Visits each state exactly once"
    },
    "Combinations": {
        "Time": "O(2^n)",
        "Space": "O(n) for recursion stack",
        "Note": "Each element has two choices"
    },
    "CSP Problems": {
        "Time": "O(d^n) where d is domain size",
        "Space": "O(n) for recursion stack",
        "Note": "Pruning can significantly improve average case"
    }
}
````
## 💡 Optimization Techniques

### 1. Early Pruning
````python
def optimized_backtrack(state):
    # Check constraints early
    if not is_valid_partial(state):
        return False
    
    if is_complete(state):
        return True
    
    for choice in sorted_choices(state):  # Sort choices for better pruning
        if is_promising(state, choice):
            apply_choice(state, choice)
            if optimized_backtrack(state):
                return True
            undo_choice(state, choice)
````
### 2. State Duplication
````python
def backtrack_with_dedup(nums: List[int]) -> List[List[int]]:
    def backtrack(start: int, curr: List[int]):
        result.append(curr[:])
        
        used = set()  # Track used numbers at this level
        for i in range(start, len(nums)):
            if nums[i] in used:  # Skip duplicates at same level
                continue
            used.add(nums[i])
            
            curr.append(nums[i])
            backtrack(i + 1, curr)
            curr.pop()
````
## 💡 Interview Tips

1.  Implementation Strategy:
    -   Always use DFS for backtracking
    -   Identify state representation clearly
    -   Track partial solutions carefully
2.  Optimization Strategy:
    -   Look for early pruning opportunities
    -   Consider sorting input for better pruning
    -   Use sets/counters for duplicate handling
3.  Problem Solving Steps:
    -   Identify what makes a valid solution
    -   Determine how to build solutions incrementally
    -   Define clear base cases
    -   Plan state tracking strategy
4.  Testing Strategy:
    -   Start with small inputs
    -   Test with duplicates if relevant
    -   Verify all solutions are found
    -   Check for invalid inputs

Remember:

-   Backtracking = Choices + Consequences
-   Think in terms of state and state changes
-   Always handle cleanup in backward pass
-   Consider space complexity of solution storage
# 🌳 Binary Trees Guide

## 📚 Core Implementation

### Basic Tree Node
````python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
````
### Common Tree Building Patterns
````python
def build_tree_examples():
    # Simple Tree
    root = TreeNode(1)
    root.left = TreeNode(2)
    root.right = TreeNode(3)
    
    # From List
    def from_list(nums: List[int], index: int = 0) -> TreeNode:
        if index >= len(nums) or nums[index] is None:
            return None
        root = TreeNode(nums[index])
        root.left = from_list(nums, 2 * index + 1)
        root.right = from_list(nums, 2 * index + 2)
        return root
````
## 🎯 Core Traversal Patterns

### 1. DFS Patterns
````python
class DFSPatterns:
    def inorder(self, root: TreeNode) -> List[int]:
        # Left -> Root -> Right
        def dfs(node):
            if not node:
                return
            dfs(node.left)        # Process left
            result.append(node.val)# Process root
            dfs(node.right)       # Process right
        
        result = []
        dfs(root)
        return result
    
    def preorder(self, root: TreeNode) -> List[int]:
        # Root -> Left -> Right
        def dfs(node):
            if not node:
                return
            result.append(node.val)# Process root
            dfs(node.left)        # Process left
            dfs(node.right)       # Process right
        
        result = []
        dfs(root)
        return result
    
    def postorder(self, root: TreeNode) -> List[int]:
        # Left -> Right -> Root
        def dfs(node):
            if not node:
                return
            dfs(node.left)        # Process left
            dfs(node.right)       # Process right
            result.append(node.val)# Process root
        
        result = []
        dfs(root)
        return result
````
### 2. BFS Pattern
````python
from collections import deque

def level_order(root: TreeNode) -> List[List[int]]:
    if not root:
        return []
    
    result = []
    queue = deque([root])
    
    while queue:
        level_size = len(queue)
        current_level = []
        
        for _ in range(level_size):
            node = queue.popleft()
            current_level.append(node.val)
            
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)
        
        result.append(current_level)
    
    return result
````
## 🎮 Common Problem Patterns

### 1. Path Problems Pattern
````python
def path_pattern(root: TreeNode):
    def dfs(node, path, target):
        if not node:
            return
        
        # Add current node to path
        path.append(node.val)
        
        # Check if leaf node
        if not node.left and not node.right:
            process_path(path)  # Process complete path
        
        # Recurse on children
        dfs(node.left, path, target)
        dfs(node.right, path, target)
        
        # Backtrack
        path.pop()
````
### 2. Binary Search Tree Pattern
````python
def bst_pattern(root: TreeNode):
    def validate_bst(node, min_val=float('-inf'), max_val=float('inf')):
        if not node:
            return True
            
        # Check BST property
        if node.val <= min_val or node.val >= max_val:
            return False
            
        # Recurse with updated bounds
        return (validate_bst(node.left, min_val, node.val) and 
                validate_bst(node.right, node.val, max_val))
````
### 3. Lowest Common Ancestor
````python
def lca_pattern(root: TreeNode, p: TreeNode, q: TreeNode):
    def find_lca(node):
        if not node or node == p or node == q:
            return node
            
        # Search in left and right subtrees
        left = find_lca(node.left)
        right = find_lca(node.right)
        
        # If found in both subtrees, current node is LCA
        if left and right:
            return node
            
        # Return non-null node
        return left or right
````
### 4. View Problems Pattern
````python
def tree_view_pattern(root: TreeNode):
    def right_view(root):
        result = []
        
        def dfs(node, level):
            if not node:
                return
                
            # First node of this level from right
            if len(result) == level:
                result.append(node.val)
                
            # Visit right first for right view
            dfs(node.right, level + 1)
            dfs(node.left, level + 1)
        
        dfs(root, 0)
        return result
````
## 🎯 Pattern Recognition Guide

### When to Use Each Pattern:

1.  **Use DFS When:**
    -   Need to process nodes in a specific order
    -   Working with paths from root to leaf
    -   Validating tree properties
    -   Computing tree properties recursively
2.  **Use BFS When:**
    -   Need level-by-level processing
    -   Finding shortest paths
    -   Working with tree width
    -   Level-based operations
3.  **Use Path Patterns When:**
    -   Need complete paths from root to leaf
    -   Summing paths
    -   Finding specific paths
    -   Path validation
4.  **Use BST Patterns When:**
    -   Searching for values
    -   Validating BST properties
    -   Range-based operations
    -   Maintaining sorted order

## 💡 Problem-Solving Strategy

1.  **Identify Pattern Type:**
    -   Is it path-based?
    -   Is it level-based?
    -   Does it involve BST properties?
    -   Is order important?
2.  **Choose Traversal Method:**
````python
patterns = {
    "Need Path": "DFS with path tracking",
    "Level Operations": "BFS with queue",
    "Specific Order": "Choose appropriate DFS order",
    "BST Operations": "Use BST properties"
}
````
3. **Consider Edge Cases**
````python
edge_cases = [
    "Empty tree",
    "Single node",
    "All nodes same value",
    "Unbalanced tree",
    "Complete binary tree"
]
````
4. **Time/Space Complexity**
````python
complexities = {
    "DFS": "Time: O(n), Space: O(h)",
    "BFS": "Time: O(n), Space: O(w)",
    "Path": "Time: O(n), Space: O(h)",
    "BST": "Time: O(h), Space: O(1) typical"
}
# where n = nodes, h = height, w = max width
````
Remember:

-   Start with traversal pattern identification
-   Consider whether order matters
-   Check if BST properties help
-   Handle edge cases explicitly

# 🌲 Tries (Prefix Trees)

## 📚 Core Implementation

### Basic Trie Node
````python
class TrieNode:
    def __init__(self):
        self.children = {}  # or [None] * 26 for fixed alphabet
        self.is_end = False  # Marks end of word
````
### Basic Trie Structure
````python
class Trie:
    def __init__(self):
        self.root = TrieNode()
    
    def insert(self, word: str) -> None:
        node = self.root
        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]
        node.is_end = True
    
    def search(self, word: str) -> bool:
        node = self.root
        for char in word:
            if char not in node.children:
                return False
            node = node.children[char]
        return node.is_end
    
    def starts_with(self, prefix: str) -> bool:
        node = self.root
        for char in prefix:
            if char not in node.children:
                return False
            node = node.children[char]
        return True
````
## 🎯 Common Patterns

### 1. Word Dictionary Pattern
````python
class WordDictionary:
    def __init__(self):
        self.root = TrieNode()
    
    def insert(self, word: str) -> None:
        node = self.root
        for char in word:
            if char not in node.children:
                node.children[char] = TrieNode()
            node = node.children[char]
        node.is_end = True
    
    def search_with_wildcard(self, word: str) -> bool:
        def dfs(node, i):
            if i == len(word):
                return node.is_end
                
            if word[i] == '.':
                for child in node.children.values():
                    if child and dfs(child, i + 1):
                        return True
                return False
            
            if word[i] not in node.children:
                return False
                
            return dfs(node.children[word[i]], i + 1)
        
        return dfs(self.root, 0)
````
### 2. Prefix Matching Pattern
````python
def prefix_matching_pattern():
    class AutocompleteSystem:
        def __init__(self, words: List[str], times: List[int]):
            self.root = TrieNode()
            self.prefix = ""
            
            # Insert words with frequencies
            for word, count in zip(words, times):
                self._insert(word, count)
        
        def _insert(self, word: str, count: int) -> None:
            node = self.root
            for char in word:
                if char not in node.children:
                    node.children[char] = TrieNode()
                node = node.children[char]
                node.counts[word] = count
        
        def input(self, c: str) -> List[str]:
            if c == '#':
                self._insert(self.prefix, 1)
                self.prefix = ""
                return []
                
            self.prefix += c
            node = self.root
            
            # Find node for current prefix
            for char in self.prefix:
                if char not in node.children:
                    return []
                node = node.children[char]
            
            # Get top 3 suggestions
            return sorted(node.counts.items(), 
                        key=lambda x: (-x[1], x[0]))[:3]
````
### 3. Word Square Pattern
````python
def word_square_pattern(words: List[str]) -> List[List[str]]:
    trie = Trie()
    n = len(words[0])
    
    # Build prefix map
    prefix_map = defaultdict(list)
    for i, word in enumerate(words):
        for j in range(len(word) + 1):
            prefix_map[word[:j]].append(i)
    
    def get_words_with_prefix(prefix):
        return [words[i] for i in prefix_map[prefix]]
    
    def backtrack(square):
        if len(square) == n:
            result.append(square[:])
            return
            
        # Get prefix for next word
        pos = len(square)
        prefix = ''.join(word[pos] for word in square)
        
        # Try all words with this prefix
        for word in get_words_with_prefix(prefix):
            square.append(word)
            backtrack(square)
            square.pop()
    
    result = []
    backtrack([])
    return result
````
## 🎯 Time/Space Complexity
````python
complexities = {
    "Insert": {
        "Time": "O(m) where m is word length",
        "Space": "O(m)"
    },
    "Search": {
        "Time": "O(m)",
        "Space": "O(1)"
    },
    "StartsWith": {
        "Time": "O(m)",
        "Space": "O(1)"
    },
    "Space Usage": "O(ALPHABET_SIZE * m * n) for n words"
}
````
## 🔑 Key Advantages/Disadvantages

### Advantages:
````python
advantages = [
    "Fast prefix lookups O(m)",
    "Space-efficient for common prefixes",
    "No need for hash function",
    "No collisions to handle",
    "Natural for autocomplete/spellcheck"
]
````
### Disadvantages
````python
disadvantages = [
    "Memory intensive (many null pointers)",
    "Slower than hash table for exact lookups",
    "Complex to implement/maintain",
    "Not cache-friendly due to pointer chasing"
]
````
## 💡 When to Use Tries
````python
use_cases = {
    "Autocomplete": "Search suggestions",
    "Spell Checker": "Word validation",
    "IP Routing": "Prefix matching",
    "Word Games": "Word validation/search",
    "Contact List": "Type-ahead search"
}
````
## ⚠️ Common Pitfalls

1.  **Memory Management**
````python
def avoid_memory_issues():
    """
    - Consider using array instead of map for fixed alphabet
    - Clean up unused nodes
    - Use compressed tries for long strings
    """
    pass
````
2. **Implementation Choices**
````python
def implementation_tips():
    """
    - Choose appropriate children structure
      (array vs map based on alphabet size)
    - Decide on case sensitivity handling
    - Plan wildcard character handling
    """
    pass
````
## 🎯 Practice Problem Types

1.  **Basic Operations**
    -   Implement insert/search/startsWith
    -   Handle wildcards
    -   Case-sensitive operations
2.  **Word Problems**
    -   Word search
    -   Word squares
    -   Word break
    -   Replace words
3.  **Prefix Problems**
    -   Autocomplete
    -   Longest common prefix
    -   Unique prefixes

Remember:

-   Consider memory-space tradeoffs
-   Handle edge cases (empty strings, special chars)
-   Think about prefix sharing opportunities
-   Consider case sensitivity requirements
# 🔍 Binary Search Guide

## 📚 Core Template

### Most Generalized Binary Search Template
````python
def binary_search(array) -> int:
    def condition(value) -> bool:
        # Customize condition here
        pass

    left, right = min(search_space), max(search_space)
    while left < right:
        mid = left + (right - left) // 2
        if condition(mid):
            right = mid
        else:
            left = mid + 1
    return left

# Key Points:
# 1. Initialize boundaries to include ALL possible answers
# 2. Condition function defines search criteria
# 3. Returns minimum k where condition(k) is True
````

## 🎯 Three Key Components

### 1. Boundary Initialization
````python
def initialize_boundaries():
    """
    Rules for setting left and right:
    1. Must include all possible answers
    2. Common patterns:
       - [0, len(array)]         # For index search
       - [min(array), max(array)] # For value search
       - [1, max_possible]       # For minimum/maximum problems
    """
    # Example bounds for different scenarios
    bounds = {
        "Index Search": (0, len(array)),
        "Value Search": (min(array), max(array)),
        "Minimum Search": (1, max_value),
        "Maximum Search": (min_value, sum(array))
    }
````
### 2. Condition Function Design
````python
def design_condition():
    """
    Patterns for condition functions:
    1. Direct Comparison: array[mid] >= target
    2. Feasibility Check: can_achieve(mid)
    3. Counting: count_less_equal(mid) >= k
    4. Validation: is_valid_solution(mid)
    """
    # Example condition patterns
    conditions = {
        "Finding Target": lambda mid: array[mid] >= target,
        "Feasibility": lambda mid: can_do_task_with_value(mid),
        "Counting": lambda mid: count_elements_less_than(mid) >= k,
        "Validation": lambda mid: validates_constraint(mid)
    }
````
### 3. Return Value Selection
````python
def choose_return():
    """
    Return value patterns:
    1. left: Minimum value satisfying condition
    2. left - 1: Maximum value not satisfying condition
    3. right: Alternative minimum value
    4. Special handling for not found cases
    """
    return_patterns = {
        "Minimum Satisfying": "return left",
        "Maximum Not Satisfying": "return left - 1",
        "Not Found": "return -1 if not found"
    }
````
## 🎮 Common Problem Patterns

### 1. Classical Binary Search
````python
def classical_search(nums: List[int], target: int) -> int:
    left, right = 0, len(nums)
    
    while left < right:
        mid = left + (right - left) // 2
        if nums[mid] >= target:
            right = mid
        else:
            left = mid + 1
    
    return left if left < len(nums) and nums[left] == target else -1
````
### 2. Minimum Value Search
````python
def find_minimum(nums: List[int]) -> int:
    def feasible(value) -> bool:
        # Define feasibility condition
        total = 0
        for num in nums:
            if condition(num, value):
                total += 1
        return total >= required

    left, right = min_possible, max_possible
    while left < right:
        mid = left + (right - left) // 2
        if feasible(mid):
            right = mid
        else:
            left = mid + 1
    return left
````
### 3. Maximum Value Search
````python
def find_maximum(nums: List[int]) -> int:
    def feasible(value) -> bool:
        # Define feasibility condition
        return can_achieve_with_value(value)

    left, right = min_possible, max_possible
    while left < right:
        mid = left + (right - left + 1) // 2  # Note: Different mid calculation
        if feasible(mid):
            left = mid
        else:
            right = mid - 1
    return left
````
## 🎯 Pattern Recognition Guide

### When to Use Binary Search:
````python
binary_search_indicators = {
    "Sorted Array": "Direct binary search possible",
    "Monotonic Condition": "Can use binary search on answer space",
    "Min/Max Optimization": "Likely binary search on result",
    "Feasibility Check": "Can binary search with validation",
    "Counting Problems": "Binary search possible if monotonic"
}
````
### Problem Type Recognition
````python
def identify_pattern(problem):
    patterns = {
        "Find Exact Value": "Classical binary search",
        "Find Minimum Satisfying": "Minimum value pattern",
        "Find Maximum Possible": "Maximum value pattern",
        "Optimization with Constraint": "Feasibility pattern",
        "Counting with Condition": "Counting pattern"
    }
````
## ⚠️ Common Pitfalls

1.  **Boundary Issues**
````python
def avoid_boundary_issues():
    """
    Common pitfalls:
    1. Off-by-one errors in boundaries
    2. Not including all possible answers
    3. Infinite loops due to improper mid calculation
    4. Not handling edge cases
    """
    pass
````
2. **Condition Design**
````python
def condition_pitfalls():
    """
    Watch out for:
    1. Non-monotonic conditions
    2. Incorrect comparison operators
    3. Missing edge cases in condition
    4. Overcomplicated condition logic
    """
    pass
````
## 💡 Implementation Tips

1.  Always use  `left + (right - left) // 2`  to avoid overflow
2.  Consider whether to include end points
3.  Test with small examples first
4.  Verify monotonicity of condition
5.  Handle edge cases explicitly

Remember:

-   Think in terms of answer space vs index space
-   Verify condition function monotonicity
-   Consider boundary cases carefully
-   Test with small inputs first

# 🪙 Greedy Algorithms

## 📚 Core Properties

### What is a Greedy Algorithm?

A greedy algorithm makes the locally optimal choice at each step, hoping to find a global optimum. While simple and intuitive, they don't always yield the optimal solution but often provide efficient solutions for optimization problems.

### Key Properties
````python
properties = {
    "Local Optimal Choice": "Best choice at current step",
    "Hope": "Local optimum leads to global optimum",
    "No Backtracking": "Decisions are final",
    "Simple Implementation": "Usually straightforward code"
}
````
## 🎯 When to Use Greedy Algorithms

### Criteria for Greedy Approach
````python
def is_greedy_applicable(problem):
    criteria = {
        "Greedy Choice Property": """Local optimal choices 
            lead to global optimal solution""",
        "Optimal Substructure": """Optimal solution contains 
            optimal solutions to subproblems""",
        "No Future Impact": "Current choice doesn't affect future choices",
        "Simple Constraints": "Problem has straightforward constraints"
    }
    return all(criteria.values())
````
## 🎮 Common Greedy Patterns

### 1. Activity Selection Pattern
````python
def activity_selection(start: List[int], finish: List[int]) -> List[int]:
    # Sort activities by finish time
    activities = sorted(zip(start, finish), key=lambda x: x[1])
    selected = [activities[0]]
    last_finish = activities[0][1]
    
    for start_time, finish_time in activities[1:]:
        if start_time >= last_finish:
            selected.append((start_time, finish_time))
            last_finish = finish_time
            
    return selected
````
### 2. Fractional Knapsack Problem
````python
def fractional_knapsack(values: List[int], weights: List[int], 
                       capacity: int) -> float:
    # Calculate value/weight ratio
    items = sorted(zip(values, weights), 
                  key=lambda x: x[0]/x[1], reverse=True)
    total_value = 0
    
    for value, weight in items:
        if capacity >= weight:
            # Take whole item
            capacity -= weight
            total_value += value
        else:
            # Take fraction of item
            total_value += value * (capacity / weight)
            break
            
    return total_value
````
### 3. Meeting Rooms Pattern
````python
def min_meeting_rooms(intervals: List[List[int]]) -> int:
    if not intervals:
        return 0
        
    # Separate start and end times
    starts = sorted([i[0] for i in intervals])
    ends = sorted([i[1] for i in intervals])
    
    rooms = 0
    max_rooms = 0
    s = e = 0
    
    while s < len(intervals):
        if starts[s] < ends[e]:
            rooms += 1
            s += 1
        else:
            rooms -= 1
            e += 1
        max_rooms = max(max_rooms, rooms)
        
    return max_rooms
````
### 4. Coin Change (Greedy Pattern)
````python
def coin_change_greedy(amount: int, coins: List[int]) -> int:
    coins.sort(reverse=True)  # Sort coins in descending order
    count = 0
    
    for coin in coins:
        while amount >= coin:
            amount -= coin
            count += 1
            
    return count if amount == 0 else -1
````

## 🔄 Universal Greedy Patterns

### 1. Sorting-First Pattern
````python
def sorting_first_pattern(items, key_function=None):
    """
    Universal pattern for problems requiring initial sorting.
    Common in: Activity selection, Job scheduling, Meeting rooms
    """
    # 1. Sort based on key metric
    sorted_items = sorted(items, key=key_function) if key_function else sorted(items)
    
    result = []
    current = sorted_items[0]  # Track current selection
    
    # 2. Process items in sorted order
    for item in sorted_items[1:]:
        if satisfies_constraint(current, item):
            # 3. Make greedy choice
            result.append(current)
            current = item
            
    result.append(current)  # Don't forget last item
    return result

# Example Usage: Activity Selection
def activity_selection(activities):
    return sorting_first_pattern(
        activities,
        key_function=lambda x: x[1]  # Sort by finish time
    )

# Example Usage: Meeting Rooms
def meeting_rooms(meetings):
    return sorting_first_pattern(
        meetings,
        key_function=lambda x: x[0]  # Sort by start time
    )
````
### 2. Fraction Rate/Pattern
````python
def fraction_pattern(items, constraint, get_value, get_weight):
    """
    Universal pattern for fractional optimization problems.
    Common in: Knapsack, Task scheduling with efficiency
    """
    # 1. Calculate rates and sort
    rates = [(get_value(item)/get_weight(item), item) 
             for item in items]
    rates.sort(reverse=True)
    
    result = []
    total_value = 0
    remaining = constraint
    
    # 2. Process items by rate
    for rate, item in rates:
        weight = get_weight(item)
        if remaining >= weight:
            # Take whole item
            result.append((item, 1.0))
            total_value += get_value(item)
            remaining -= weight
        else:
            # Take fraction
            fraction = remaining / weight
            result.append((item, fraction))
            total_value += get_value(item) * fraction
            break
            
    return result, total_value

# Example Usage: Fractional Knapsack
def fractional_knapsack(items, capacity):
    return fraction_pattern(
        items,
        capacity,
        get_value=lambda x: x.value,
        get_weight=lambda x: x.weight
    )
````
### 3. Running Window Pattern
````python
def running_window_pattern(items, constraint):
    """
    Universal pattern for running window problems.
    Common in: Meeting rooms, Task scheduling, Resource allocation
    """
    # 1. Separate start and end events
    events = []
    for start, end in items:
        events.append((start, 1))   # 1 for start
        events.append((end, -1))    # -1 for end
    
    # 2. Sort events
    events.sort()
    
    current = 0
    max_needed = 0
    
    # 3. Process events in order
    for time, change in events:
        current += change
        max_needed = max(max_needed, current)
        
        if max_needed > constraint:
            return False
            
    return True

# Example Usage: Meeting Rooms
def can_schedule_meetings(meetings, available_rooms):
    return running_window_pattern(meetings, available_rooms)
````
### 4. Local Exchange Pattern
````python
def local_exchange_pattern(items):
    """
    Universal pattern for local optimization problems.
    Common in: Job scheduling, Task optimization
    """
    result = list(items)  # Create mutable copy
    made_change = True
    
    while made_change:
        made_change = False
        for i in range(len(result) - 1):
            # Compare adjacent items
            if better_exchange(result[i], result[i + 1]):
                result[i], result[i + 1] = result[i + 1], result[i]
                made_change = True
                
    return result

# Example Usage: Job Sequencing
def job_sequencing(jobs):
    def better_exchange(job1, job2):
        return (job1.profit/job1.deadline < 
                job2.profit/job2.deadline)
    
    return local_exchange_pattern(jobs)
````
### 5. Priority Queue Pattern
````python
from heapq import heappush, heappop

def priority_queue_pattern(items, k):
    """
    Universal pattern for k-selection problems.
    Common in: K closest points, Top K frequent elements
    """
    heap = []
    
    for item in items:
        # Maintain heap of size k
        if len(heap) < k:
            heappush(heap, item)
        else:
            if better_than_top(item, heap[0]):
                heappop(heap)
                heappush(heap, item)
                
    return sorted(heap)  # Return sorted result

# Example Usage: K Closest Points
def k_closest_points(points, k):
    return priority_queue_pattern(
        points,
        k=k
    )
````
### Pattern Selection Guide
````python
pattern_guide = {
    "Sorting-First": {
        "Use When": [
            "Items need to be processed in specific order",
            "Selection based on sorted property",
            "No overlapping allowed"
        ],
        "Examples": [
            "Activity selection",
            "Meeting rooms",
            "Task scheduling"
        ]
    },
    "Fraction/Rate": {
        "Use When": [
            "Divisible items",
            "Optimization based on rates",
            "Knapsack-like problems"
        ],
        "Examples": [
            "Fractional knapsack",
            "Resource allocation",
            "Time management"
        ]
    },
    "Running Window": {
        "Use When": [
            "Time/Space intervals",
            "Resource constraints",
            "Overlapping intervals"
        ],
        "Examples": [
            "Meeting rooms",
            "CPU scheduling",
            "Resource booking"
        ]
    },
    "Local Exchange": {
        "Use When": [
            "Local optimization possible",
            "Pairwise comparisons sufficient",
            "Order matters"
        ],
        "Examples": [
            "Job sequencing",
            "Task ordering",
            "Optimization problems"
        ]
    },
    "Priority Queue": {
        "Use When": [
            "K-selection problems",
            "Running minimum/maximum",
            "Stream processing"
        ],
        "Examples": [
            "K closest points",
            "Top K elements",
            "Running median"
        ]
    }
}
````




## 🎯 Problem-Solving Framework

### 1. Verify Greedy Approach
````python
def verify_greedy_approach():
    checks = {
        "Local Choice": "Can we make locally optimal choice?",
        "Subproblem": "Does it lead to simpler subproblem?",
        "Optimality": "Do local choices lead to global optimum?",
        "Constraints": "Are constraints simple and local?"
    }
````
### 2. Design Steps

1.  **Sort if Needed**
    -   Often first step is sorting by key metric
    -   Examples: finish time, value/weight ratio
2.  **Define Greedy Choice**
    -   What makes a choice locally optimal?
    -   How to select next element?
3.  **Implement Selection Process**
    -   Process elements in sorted order
    -   Apply greedy choice at each step
4.  **Track Progress/Result**
    -   Maintain running solution
    -   Update constraints

## ⚠️ Common Pitfalls

### 1. Verification Issues
````python
pitfalls = {
    "Optimality": "Not verifying if greedy leads to optimal",
    "Constraints": "Missing important constraints",
    "Sorting": "Wrong sorting criteria",
    "Edge Cases": "Not handling edge cases"
}
````
### 2. Implementation Issues
````python
implementation_issues = {
    "Initialization": "Incorrect initial values",
    "Updates": "Wrong progress tracking",
    "Termination": "Incorrect stopping condition",
    "Optimization": "Missing optimization opportunities"
}
````
## 📝 Common Interview Problems

### 1. Scheduling Problems

-   Activity Selection
-   Meeting Rooms
-   Task Scheduling

### 2. Optimization Problems

-   Fractional Knapsack
-   Minimum Coins
-   Huffman Coding

### 3. Connection Problems

-   Minimum Spanning Tree
-   Job Sequencing
-   Shortest Path (Dijkstra's)

## 💡 Interview Tips

1.  **Approach**
    -   Start with greedy hypothesis
    -   Prove/disprove with examples
    -   Consider sorting first
    -   Track progress clearly
2.  **Verification**
    -   Use small examples
    -   Find counter-examples
    -   Explain why greedy works
3.  **Implementation**
    -   Keep code clean and simple
    -   Handle edge cases
    -   Consider optimization
    -   Test with various inputs

## 🎯 Time Complexity Analysis
````python
complexities = {
    "Sorting Based": "O(n log n) typical",
    "Linear Scan": "O(n) without sorting",
    "Priority Queue": "O(n log k) for k elements",
    "Space": "Usually O(1) or O(n)"
}
````
Remember:

-   Greedy algorithms are simple but not always optimal
-   Verify greedy choice property
-   Consider sorting as first step
-   Handle edge cases carefully

# 🎯 Dynamic Programming - From Fundamentals to Mastery

## 📚 Introduction to Dynamic Programming

### What is Dynamic Programming?

Dynamic Programming (DP) is both a mathematical optimization method and a programming method that:

1.  Breaks down complex problems into simpler subproblems
2.  Stores solutions to these subproblems to avoid recalculating them
3.  Uses stored solutions to build up to the final solution

Think of it as "careful brute force" - instead of recalculating values we've seen before, we save them for later use.

### When to Use Dynamic Programming
````python
criteria_for_dp = {
    "1. Optimal Substructure": """
        Can the problem be broken down into smaller problems?
        Example: Fibonacci numbers - F(n) depends on F(n-1) and F(n-2)
        """,
    "2. Overlapping Subproblems": """
        Do we calculate the same things repeatedly?
        Example: In Fibonacci, F(5) and F(4) both need F(3)
        """,
    "3. No Greedy Choice": """
        Does making the locally optimal choice not always lead to global optimal?
        Example: Coin change problem with coins [1, 15, 25]
        """
}
````
## 🎯 Core Concepts Explained

### 1. Subproblems and Optimal Substructure
````python
def understand_subproblems():
    """
    Example: Finding F(4) in Fibonacci sequence
    
    F(4) = F(3) + F(2)     # Main problem
    F(3) = F(2) + F(1)     # Subproblem
    F(2) = F(1) + F(0)     # Smaller subproblem
    
    Properties:
    1. Each subproblem is smaller version of main problem
    2. Solution to main problem depends on subproblems
    3. Base cases stop the recursion
    """
    pass
````
### 2. Overlapping Subproblems
````python
def show_overlapping_example(n: int):
    """
    Without DP (lots of repeated calculations):
    F(5)
    ├── F(4)
    │   ├── F(3)
    │   │   ├── F(2)  # Calculated multiple times
    │   │   └── F(1)
    │   └── F(2)      # Calculated again
    └── F(3)
        ├── F(2)      # Calculated yet again
        └── F(1)
    
    With DP (calculate once, reuse result):
    memo = {
        0: 0,
        1: 1,
        2: F(2),  # Calculate once, reuse many times
        3: F(3),
        ...
    }
    """
    pass
````
## 🎮 Two Main Approaches to DP

### 1. Top-Down (Memoization)
````python
def explain_memoization():
    """
    Top-Down Process:
    1. Start with original problem (top)
    2. Break into subproblems recursively
    3. Store results in memo table
    4. Return memoized results if subproblem seen before
    
    Advantages:
    - More intuitive (follows natural thinking)
    - Only solves needed subproblems
    - Easier to debug
    
    Disadvantages:
    - Recursion overhead
    - Stack space usage
    """
    # Example implementation
    def fib_memo(n: int, memo: dict = None) -> int:
        if memo is None:
            memo = {}
            
        # Base cases
        if n <= 1:
            return n
            
        # Check memo before computing
        if n in memo:
            return memo[n]
            
        # Store result in memo
        memo[n] = fib_memo(n-1, memo) + fib_memo(n-2, memo)
        return memo[n]
````
### 2. Bottom-Up (Tabulation)
````python
def explain_tabulation():
    """
    Bottom-Up Process:
    1. Start with base cases (bottom)
    2. Build larger solutions from smaller ones
    3. Store results in table
    4. Use table to build final solution
    
    Advantages:
    - More space efficient
    - No recursion overhead
    - Better cache performance
    
    Disadvantages:
    - May solve unnecessary subproblems
    - Sometimes less intuitive
    """
    # Example implementation
    def fib_table(n: int) -> int:
        if n <= 1:
            return n
            
        # Initialize table with base cases
        dp = [0] * (n + 1)
        dp[1] = 1
        
        # Build up the solution
        for i in range(2, n + 1):
            dp[i] = dp[i-1] + dp[i-2]
            
        return dp[n]
````
## 🎯 Problem-Solving Framework

### Step 1: Identify DP Characteristics
````python
def identify_dp_potential(problem):
    """
    Ask these questions:
    1. Can I break this into smaller similar subproblems?
    2. Does solving subproblems help solve the original problem?
    3. Am I calculating same things repeatedly?
    4. Can I store and reuse these calculations?
    """
    checklist = {
        "Optimal Substructure": False,
        "Overlapping Subproblems": False,
        "Need for Optimization": False
    }
    return all(checklist.values())
````
### Step 2: Define the Subproblem
````python
def define_subproblem():
    """
    1. State Definition:
    - What variables define a subproblem?
    - What information needed to solve it?
    
    2. State Transition:
    - How do I move from one state to another?
    - What choices do I have at each state?
    
    Example (Knapsack):
    - State: dp[i][w] = max value using items[0..i] with weight limit w
    - Transition: Choose whether to include item i or not
    """
    pass
````
### Step 3: Write the Recurrence Relation
````python
def create_recurrence():
    """
    1. Base Cases:
    - Smallest possible subproblem
    - Starting point for computation
    
    2. Recurrence Formula:
    - How larger problems relate to smaller ones
    - Mathematical relationship between states
    
    Example (Knapsack):
    dp[i][w] = max(
        dp[i-1][w],                    # Don't take item
        dp[i-1][w-weight[i]] + val[i]  # Take item
    )
    """
    pass
````
### Step 4: Implement Solution
````python
def implement_solution():
    """
    Choose Implementation Style:
    1. Top-Down if:
    - Natural recursive solution
    - Not all subproblems needed
    - Need to debug/understand easily
    
    2. Bottom-Up if:
    - Need to optimize space
    - All subproblems needed
    - Want to avoid recursion
    """
    pass
````
## 🎯 Common DP Patterns

### 1. Linear Sequence

Used when each state depends on previous states.
````python
def linear_dp_example():
    # Example: House Robber Problem
    def rob(nums: List[int]) -> int:
        if not nums:
            return 0
        if len(nums) == 1:
            return nums[0]
            
        dp = [0] * len(nums)
        dp[0] = nums[0]
        dp[1] = max(nums[0], nums[1])
        
        for i in range(2, len(nums)):
            dp[i] = max(dp[i-1], dp[i-2] + nums[i])
            
        return dp[-1]
````
### 2. Matrix Chain

Used for optimization problems involving sequences.
````python
def matrix_chain_example():
    # Example: Matrix Chain Multiplication
    def matrix_mult_cost(dimensions: List[int]) -> int:
        n = len(dimensions) - 1
        dp = [[0] * n for _ in range(n)]
        
        for length in range(2, n + 1):
            for i in range(n - length + 1):
                j = i + length - 1
                dp[i][j] = float('inf')
                for k in range(i, j):
                    cost = (dp[i][k] + dp[k+1][j] + 
                           dimensions[i] * dimensions[k+1] * dimensions[j+1])
                    dp[i][j] = min(dp[i][j], cost)
                    
        return dp[0][n-1]
````
### 3. Interval Problems

Used when dealing with ranges or intervals.
````python
def interval_dp_example():
    # Example: Palindrome Partitioning
    def min_cuts(s: str) -> int:
        n = len(s)
        # is_palindrome[i][j] tells if s[i:j+1] is palindrome
        is_palindrome = [[False] * n for _ in range(n)]
        
        # Single letters are palindromes
        for i in range(n):
            is_palindrome[i][i] = True
            
        # Check for palindromes of length 2 and more
        for length in range(2, n + 1):
            for start in range(n - length + 1):
                end = start + length - 1
                if length == 2:
                    is_palindrome[start][end] = (s[start] == s[end])
                else:
                    is_palindrome[start][end] = (
                        s[start] == s[end] and 
                        is_palindrome[start+1][end-1]
                    )
                    
        # dp[i] = minimum cuts needed for s[0:i+1]
        dp = [0] * n
        for i in range(n):
            if is_palindrome[0][i]:
                dp[i] = 0
            else:
                dp[i] = i
                for j in range(i):
                    if is_palindrome[j+1][i]:
                        dp[i] = min(dp[i], dp[j] + 1)
                        
        return dp[n-1]
````
## 💡 Advanced Optimization Techniques

### 1. Space Optimization
````python
def space_optimization_example():
    """
    Common Techniques:
    1. Rolling Array
    - Keep only last k states
    - Use mod operator for indexing
    
    2. State Compression
    - Use bits to represent states
    - Reduce dimension of dp table
    
    Example: Fibonacci with O(1) space
    """
    def fib_optimized(n: int) -> int:
        if n <= 1:
            return n
        a, b = 0, 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return b
````
### 2. State Reduction
````python
def state_reduction_example():
    """
    Techniques:
    1. Eliminate Redundant States
    - Identify states that can be derived
    - Combine overlapping states
    
    2. Change State Representation
    - More efficient encoding
    - Different perspective on problem
    
    Example: Reducing 2D DP to 1D
    """
    # Original 2D Knapsack
    def knapsack_2d(weights: List[int], values: List[int], capacity: int) -> int:
        n = len(weights)
        dp = [[0] * (capacity + 1) for _ in range(n + 1)]
        
        for i in range(1, n + 1):
            for w in range(capacity + 1):
                if weights[i-1] <= w:
                    dp[i][w] = max(values[i-1] + dp[i-1][w-weights[i-1]], 
                                 dp[i-1][w])
                else:
                    dp[i][w] = dp[i-1][w]
        return dp[n][capacity]
    
    # Optimized 1D Knapsack
    def knapsack_1d(weights: List[int], values: List[int], capacity: int) -> int:
        dp = [0] * (capacity + 1)
        
        for i in range(len(weights)):
            for w in range(capacity, weights[i]-1, -1):
                dp[w] = max(dp[w], dp[w-weights[i]] + values[i])
        return dp[capacity]
````
Remember:

-   Always start with a clear understanding of subproblems
-   Draw out the recurrence relation
-   Consider both top-down and bottom-up approaches
-   Look for optimization opportunities
-   Test with small cases first

### Reference
[Dynamic Programming](https://youtu.be/aPQY__2H3tE?si=kF10ZwFUbYQa1s0B)
# 📊 Graphs & Graph Theory

## 📚 Core Concepts

### What is a Graph?

A graph is a data structure consisting of:

-   **Vertices (Nodes)**: Points in the graph
-   **Edges**: Connections between vertices
-   **Optional Properties**: Weights, directions, labels

Types of Graphs:
````python
graph_types = {
    "Undirected": "Edges have no direction (Facebook friendships)",
    "Directed": "Edges have direction (Twitter follows)",
    "Weighted": "Edges have weights (Road distances)",
    "Connected": "Path exists between any two vertices",
    "Cyclic": "Contains at least one cycle",
    "Acyclic": "Contains no cycles (trees are acyclic)"
}
````
## 🎯 Graph Representations

### 1. Adjacency List (Most Common in Interviews)
````python
class Graph:
    def __init__(self):
        self.graph = {}
    
    def add_vertex(self, vertex):
        if vertex not in self.graph:
            self.graph[vertex] = set()
            
    def add_edge(self, v1, v2):
        if v1 not in self.graph:
            self.add_vertex(v1)
        if v2 not in self.graph:
            self.add_vertex(v2)
        self.graph[v1].add(v2)
        self.graph[v2].add(v1)  # Remove for directed graph
````
### 2. Adjacency Matrix
````python
class GraphMatrix:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0] * vertices for _ in range(vertices)]
    
    def add_edge(self, v1, v2, weight=1):
        self.graph[v1][v2] = weight
        self.graph[v2][v1] = weight  # Remove for directed graph
````

## 🎮 Essential Graph Operations

### 1. Graph Traversal

### BFS (Breadth-First Search)
````python
from collections import deque

def bfs(graph, start):
    """
    Time: O(V + E)
    Space: O(V)
    Use when:
    - Finding shortest paths
    - Level-by-level traversal
    - Finding nodes at distance k
    """
    visited = set([start])
    queue = deque([start])
    
    while queue:
        vertex = queue.popleft()
        
        for neighbor in graph[vertex]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
    
    return visited
````
### DFS (Depth-First Search)
````python
def dfs(graph, start, visited=None):
    """
    Time: O(V + E)
    Space: O(V)
    Use when:
    - Finding paths/cycles
    - Exhaustively exploring paths
    - Topological sorting
    """
    if visited is None:
        visited = set()
        
    visited.add(start)
    
    for neighbor in graph[start]:
        if neighbor not in visited:
            dfs(graph, neighbor, visited)
    return visited

# Iterative DFS (often preferred in interviews)
def dfs_iterative(graph, start):
    visited = set()
    stack = [start]
    
    while stack:
        node = stack.pop()
        if node not in visited:
            visited.add(node)
            stack.extend(neighbor for neighbor in graph[node] 
                        if neighbor not in visited)
    return visited
````
### 2. Path Finding

### Find Path Between Two Vertices
````python
def find_path(graph, start, end, path=None):
    if path is None:
        path = []
    path = path + [start]
    
    if start == end:
        return path
    
    for neighbor in graph[start]:
        if neighbor not in path:
            new_path = find_path(graph, neighbor, end, path)
            if new_path:
                return new_path
    return None
````
### Find All Paths
````python
def find_all_paths(graph, start, end, path=None):
    if path is None:
        path = []
    path = path + [start]
    
    if start == end:
        return [path]
    
    paths = []
    for neighbor in graph[start]:
        if neighbor not in path:
            new_paths = find_all_paths(graph, neighbor, end, path)
            paths.extend(new_paths)
    return paths
````
## 🎯 Common Graph Algorithms for Interviews

### 1. Detect Cycle
````python
def has_cycle(graph):
    visited = set()
    rec_stack = set()
    
    def dfs_cycle(vertex):
        visited.add(vertex)
        rec_stack.add(vertex)
        
        for neighbor in graph[vertex]:
            if neighbor not in visited:
                if dfs_cycle(neighbor):
                    return True
            elif neighbor in rec_stack:
                return True
        
        rec_stack.remove(vertex)
        return False
    
    for vertex in graph:
        if vertex not in visited:
            if dfs_cycle(vertex):
                return True
    return False
````
### 2. Topological Sort
````python
def topological_sort(graph):
    """
    For directed acyclic graphs (DAGs)
    Time: O(V + E)
    Space: O(V)
    Use when:
    - Scheduling with dependencies
    - Build systems
    - Course prerequisites
    """
    def dfs(node):
        if node in visited:
            return
        visited.add(node)
        
        for neighbor in graph[node]:
            dfs(neighbor)
        result.append(node)
    
    visited = set()
    result = []
    
    for node in graph:
        dfs(node)
    
    return result[::-1]  # Reverse for correct order

# Alternative: Kahn's Algorithm (BFS-based)
def topological_sort_kahn(graph):
    in_degree = {node: 0 for node in graph}
    for node in graph:
        for neighbor in graph[node]:
            in_degree[neighbor] += 1
    
    queue = deque([node for node, degree in in_degree.items() if degree == 0])
    result = []
    
    while queue:
        node = queue.popleft()
        result.append(node)
        
        for neighbor in graph[node]:
            in_degree[neighbor] -= 1
            if in_degree[neighbor] == 0:
                queue.append(neighbor)
    
    return result if len(result) == len(graph) else []  # Check for cycles
````
### 3. Connected Components
````python
def find_connected_components(graph):
    def dfs_component(vertex, component):
        visited.add(vertex)
        component.append(vertex)
        
        for neighbor in graph[vertex]:
            if neighbor not in visited:
                dfs_component(neighbor, component)
    
    visited = set()
    components = []
    
    for vertex in graph:
        if vertex not in visited:
            current_component = []
            dfs_component(vertex, current_component)
            components.append(current_component)
    
    return components
````

### 4. Shortest Path Algorithms
#### Dijkstra's Algorithm
````python
import heapq

def dijkstra(graph, start):
    """
    For weighted graphs with non-negative edges
    Time: O((V + E) log V)
    Space: O(V)
    Use when:
    - Finding shortest paths
    - Network routing
    - GPS navigation
    """
    distances = {vertex: float('infinity') for vertex in graph}
    distances[start] = 0
    pq = [(0, start)]
    
    while pq:
        current_distance, current = heapq.heappop(pq)
        
        if current_distance > distances[current]:
            continue
            
        for neighbor, weight in graph[current].items():
            distance = current_distance + weight
            
            if distance < distances[neighbor]:
                distances[neighbor] = distance
                heapq.heappush(pq, (distance, neighbor))
                
    return distances
````

### 5. Union Find (Disjoint Set)
````python
class UnionFind:
    """
    Time: O(α(n)) per operation (practically O(1))
    Space: O(n)
    Use when:
    - Finding connected components
    - Cycle detection
    - Minimum spanning trees
    """
    def __init__(self, size):
        self.parent = list(range(size))
        self.rank = [0] * size
    
    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])  # Path compression
        return self.parent[x]
    
    def union(self, x, y):
        px, py = self.find(x), self.find(y)
        if px == py:
            return False
        
        # Union by rank
        if self.rank[px] < self.rank[py]:
            self.parent[px] = py
        elif self.rank[px] > self.rank[py]:
            self.parent[py] = px
        else:
            self.parent[py] = px
            self.rank[px] += 1
        return True
````



## 📝 Interview Problem Patterns

### 1. Graph Traversal Problems

-   Visiting all nodes/edges
-   Finding connected components
-   Level-order traversal
````python
traversal_tips = {
    "BFS": "Use when:- Finding shortest path- Level by level traversal- Minimum steps",
    "DFS": "Use when:- Exploring paths- Finding cycles- Topological sorting",
    "Edge Cases": "- Empty graph- Single node- Disconnected components"
}
````
### 2. Path Finding Problems

-   Shortest path
-   All possible paths
-   Path with constraints
````python
def shortest_path(graph, start, end):
    queue = deque([(start, [start])])
    visited = {start}
    
    while queue:
        vertex, path = queue.popleft()
        if vertex == end:
            return path
            
        for neighbor in graph[vertex]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append((neighbor, path + [neighbor]))
    return None
````

## 💡 Interview Tips

1.  **Representation Choice**
````python
choosing_representation = {
    "Adjacency List": "- Sparse graphs- Memory efficient- Quick neighbor lookup",
    "Adjacency Matrix": "- Dense graphs- Quick edge weight lookup- Simple implementation"
}
````
2. **Algorithm Selection**
````python
algorithm_selection = {
    "BFS": "Shortest path in unweighted graph",
    "DFS": "Path finding, cycle detection",
    "Dijkstra": "Shortest path in weighted graph",
    "Union Find": "Connected components, cycle detection in undirected graph"
}
````
````python
selection_guide = {
    "Shortest Path (Unweighted)": "Use BFS",
    "Shortest Path (Weighted, Non-negative)": "Use Dijkstra",
    "Shortest Path (Weighted, Can be negative)": "Use Bellman-Ford",
    "Cycle Detection": "Use DFS with recursion stack",
    "Component Finding": "Use Union Find or DFS",
    "Dependency Ordering": "Use Topological Sort",
    "Two-Coloring Problems": "Use Bipartite Check"
}
````
3. **Edge Cases to Consider**
````python
edge_cases = [
    "Empty graph",
    "Single node",
    "Disconnected components",
    "Cycles",
    "Self-loops",
    "Bidirectional edges",
    "No path exists"
]
````

4.  **Optimization Tips**:

-   Use adjacency list for sparse graphs
-   Use adjacency matrix for dense graphs
-   Consider using iterative DFS instead of recursive for large graphs
-   Use Union Find for dynamic connectivity problems
-   Cache results in graph traversal when possible

Remember:

-   Always clarify the graph properties (directed/undirected, weighted/unweighted)
-   Consider time/space complexity tradeoffs
-   Draw examples when solving
-   Test with small cases first
-   Consider using helper functions for complex logic

# 🌳 Minimum Spanning Trees (MST)

## 📚 Core Concepts

### What is a Minimum Spanning Tree?
````python
"""
A Minimum Spanning Tree (MST) is a subset of edges in a connected, 
undirected, weighted graph that:
1. Connects all vertices
2. Contains no cycles
3. Has minimum total edge weight among all possible spanning trees

Properties:
- Contains exactly V-1 edges (where V is number of vertices)
- May not be unique (graph can have multiple MSTs)
- Always unique if all edge weights are different
"""
````
## 🎯 Key Algorithms

### 1. Kruskal's Algorithm
````python
class UnionFind:
    def __init__(self, size):
        self.parent = list(range(size))
        self.rank = [0] * size
    
    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])  # Path compression
        return self.parent[x]
    
    def union(self, x, y):
        px, py = self.find(x), self.find(y)
        if px == py:
            return False
        # Union by rank
        if self.rank[px] < self.rank[py]:
            self.parent[px] = py
        elif self.rank[px] > self.rank[py]:
            self.parent[py] = px
        else:
            self.parent[py] = px
            self.rank[px] += 1
        return True

def kruskal_mst(graph, V):
    """
    Time: O(E log E) where E is number of edges
    Space: O(V) where V is number of vertices
    
    Use when:
    - Graph is sparse (E << V²)
    - Graph might not be connected
    - Edge weights are primary consideration
    """
    edges = []  # (weight, u, v)
    for u in range(V):
        for v, w in graph[u]:
            edges.append((w, u, v))
    
    edges.sort()  # Sort by weight
    uf = UnionFind(V)
    mst = []
    mst_weight = 0
    
    for weight, u, v in edges:
        if uf.union(u, v):  # If no cycle is created
            mst.append((u, v))
            mst_weight += weight
            if len(mst) == V - 1:
                break
    
    return mst, mst_weight
````
### 2. Prim's Algorithm
````python
from heapq import heappush, heappop

def prim_mst(graph, V):
    """
    Time: O(E log V) with min-heap
    Space: O(V)
    
    Use when:
    - Graph is dense (E ≈ V²)
    - Graph is guaranteed to be connected
    - Starting vertex is known/important
    """
    visited = [False] * V
    min_heap = [(0, 0, -1)]  # (weight, vertex, parent)
    mst = []
    mst_weight = 0
    
    while min_heap:
        weight, vertex, parent = heappop(min_heap)
        
        if visited[vertex]:
            continue
            
        visited[vertex] = True
        if parent != -1:
            mst.append((parent, vertex))
            mst_weight += weight
            
        for next_vertex, edge_weight in graph[vertex]:
            if not visited[next_vertex]:
                heappush(min_heap, (edge_weight, next_vertex, vertex))
    
    return mst, mst_weight
````
## 🎮 Algorithm Selection Guide

### When to Use Each Algorithm
````python
def choose_mst_algorithm(graph_properties):
    selection_guide = {
        "Kruskal": {
            "Best for": [
                "Sparse graphs (E << V²)",
                "When graph might be disconnected",
                "When edge weights are the focus"
            ],
            "Advantages": [
                "Works with disconnected graphs",
                "Tends to be simpler to implement",
                "Good for sparse graphs"
            ]
        },
        "Prim": {
            "Best for": [
                "Dense graphs (E ≈ V²)",
                "When starting vertex matters",
                "When graph is connected"
            ],
            "Advantages": [
                "Better for dense graphs",
                "Can find partial MSTs",
                "More efficient with priority queue"
            ]
        }
    }
````
## 📝 Common Interview Problems

### 1. Connecting Cities with Minimum Cost
````python
def min_cost_connect_cities(connections, N):
    """
    Given a list of connections [city1, city2, cost],
    find minimum cost to connect all cities
    """
    def find(x):
        if parent[x] != x:
            parent[x] = find(parent[x])
        return parent[x]
    
    def union(x, y):
        px, py = find(x), find(y)
        if px == py:
            return False
        parent[px] = py
        return True
    
    parent = list(range(N + 1))
    connections.sort(key=lambda x: x[2])  # Sort by cost
    
    total_cost = 0
    edges_used = 0
    
    for city1, city2, cost in connections:
        if union(city1, city2):
            total_cost += cost
            edges_used += 1
    
    return total_cost if edges_used == N - 1 else -1
````
### 2. Network Optimization
````python
def optimize_network(nodes, connections):
    """
    Optimize network connections while maintaining
    minimum latency between all nodes
    """
    def mst_with_constraints(edges):
        uf = UnionFind(len(nodes))
        mst = []
        total_latency = 0
        
        for u, v, latency in sorted(edges, key=lambda x: (x[2], x[0])):
            if uf.union(u, v):
                mst.append((u, v))
                total_latency += latency
                
        return mst, total_latency if len(mst) == len(nodes) - 1 else float('inf')
````
## 💡 Interview Tips

### 1. Problem Recognition
````python
mst_indicators = {
    "Minimum cost/distance/weight": "Total weight needs to be minimized",
    "Connect all points": "Need spanning tree property",
    "No cycles allowed": "Tree structure required",
    "Optimize network": "Network optimization problems",
    "Reduce redundancy": "Remove unnecessary edges"
}
````
### 2. Implementation Strategy
````python
implementation_tips = {
    "1. Graph Representation": [
        "Adjacency list for sparse graphs",
        "Adjacency matrix for dense graphs",
        "Edge list for Kruskal's"
    ],
    "2. Edge Cases": [
        "Empty graph",
        "Single node",
        "Disconnected components",
        "Equal edge weights"
    ],
    "3. Optimization": [
        "Use Union-Find for cycle detection",
        "Priority queue for Prim's",
        "Sort edges once for Kruskal's"
    ]
}
````
### 3. Common Mistakes to Avoid
````python
common_mistakes = {
    "Algorithm Selection": "Not considering graph density",
    "Cycle Detection": "Forgetting to check for cycles",
    "Edge Processing": "Not handling duplicate edges",
    "Disconnected Graphs": "Assuming graph is connected",
    "Edge Weights": "Not handling negative weights"
}
````
Remember:

-   Always verify if graph is connected when using Prim's
-   Consider edge cases (empty graph, single node)
-   Watch for negative edge weights
-   Check if all vertices are included in final MST
-   Consider trade-offs between algorithms based on graph properties

# Technical Interview Patterns
[Common Technical Interview Patterns](https://blog.algomaster.io/p/15-leetcode-patterns)

