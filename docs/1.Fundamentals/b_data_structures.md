
# Data Structures
## 📘 Introduction
Data structures are specialized formats for organizing, processing, retrieving, and storing data. Understanding data structures is fundamental to writing efficient and scalable code. This guide explores various data structures, their implementations, and practical applications in software development.

### Why Data Structures Matter
-   **Efficient Problem-Solving**: Choosing the right data structure can dramatically improve program performance
-   **Career Development**: Essential for technical interviews at top tech companies
-   **Code Optimization**: Enables writing more efficient and maintainable code
-   **Real-World Applications**: Critical for building scalable software systems
-   **Competitive Edge**: Fundamental for algorithmic problem-solving and competitions

### Guide Structure
Each data structure section will cover:
- Core concepts and characteristics
- Implementation details
- Time and space complexities
- Common operations
- Best practices and use cases
- Code examples and tips
  
### Categories of Data Structures
#### Linear Data Structures
Structures where elements are stored sequentially:

-   **Arrays & ArrayLists**:
    -   Direct access by index
    -   Contiguous memory storage
    -   Best for: Fixed-size collections with frequent access
-   **Linked Lists**:
    -   Dynamic size
    -   Non-contiguous storage
    -   Best for: Frequent insertions/deletions
-   **Stacks**:
    -   LIFO (Last-In-First-Out)
    -   Best for: Function calls, undo operations
-   **Queues**:
    -   FIFO (First-In-First-Out)
    -   Best for: Task scheduling, resource management

#### Tree-Based Structures
Hierarchical structures with parent-child relationships:

- **Priority Queues**:
    -   Efficient priority-based operations
    -   Best for: Scheduling, event handling
-   **Binary Trees**:
    -   Two children per node maximum
    -   Best for: Hierarchical data
-   **Binary Search Trees**:
    -   Ordered nodes
    -   Best for: Fast search, insert, delete

#### Advanced Tree-Based Structures
Specialized tree structures for specific use cases:

-   **AVL Trees**: Balanced binary search trees    
- **Red-Black Trees**: Balanced search with color properties
-   **2-3 Trees**: Guaranteed balanced search trees
-   **B-Trees**: Optimized for disk storage
-   **K-D Trees**: Space partitioning structure
-   **M-Ary Trees**: Nodes with multiple children
#### Hash-Based Structures
Structures using hash functions:

-   **Hash Tables**:
    -   Key-value storage
    -   O(1) average access
    -   Best for: Caching, dictionaries

#### Graph-Based Structures
Structures representing connections:

-   **Directed Graphs**: One-way connections
-   **Undirected Graphs**: Two-way connections
-   **inaphs** Coctions with costs
-   **Disjoint-Sets**: Non-Overlapping group connections




#### Advanced Structures
Specialized data structures:

-   **Tries**:
    -   Efficient string operations
    -   Best for: Autocomplete, spell checkers
-   **Skip Lists**:
    -   Probabilistic alternative to balanced trees
    -   Best for: Fast search with simple implementation

### Time Complexity Overview


#### 📊 Performance Overview

| Data Structure | Access | Search | Insertion | Deletion | Space |
|----------------|---------|---------|------------|-----------|--------|
| Array | O(1) | O(n) | O(n) | O(n) | O(n) |
| ArrayList | O(1) | O(n) | O(n)* | O(n) | O(n) |
| LinkedList | O(n) | O(n) | O(1) | O(1) | O(n) |
| Stack | O(n) | O(n) | O(1) | O(1) | O(n) |
| Queue | O(n) | O(n) | O(1) | O(1) | O(n) |
| Priority Queue | O(1)*** | O(n) | O(log n) | O(log n) | O(n) |
| Binary Tree | O(n) | O(n) | O(n) | O(n) | O(n) |
| Binary Search Tree | O(log n)* | O(log n)* | O(log n)* | O(log n)* | O(n) |
| AVL Tree | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| Red-Black Tree | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| 2-3 Tree | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| B-Tree | O(log n) | O(log n) | O(log n) | O(log n) | O(n) |
| K-D Tree | O(n) | O(log n)** | O(log n)** | O(log n)** | O(n) |* | O(n) |
| Trie | O(m)**** | O(m)**** | O(m)**** | O(m)**** | O(n*m) |
| Skip List | O(log n)** | O(log n)** | O(log n)** | O(log n)** | O(n log n)
| Hash Table | O(1)** | O(1)** | O(1)** | O(1)*


\* Average case for balanced trees
\** Average case, assumes good hash function or balanced structure
\*** For peek operation only
\**** Where m is the length of the string/pattern
† Amortized time complexity for dynamic resizing~~

 

#### References
[Data Structures and Algorithms Notes](https://drive.google.com/file/d/1LaF74WE-jMvdlZ0FLwSWRxKVjO75iv8z/view?usp=share_link)
#  LINEAR DATA STRUCTURES
## ArrayList
An ArrayList is a dynamic array implementation that automatically handles resizing as elements are added or removed. It provides fast random access and is one of the most used data structures in Java.
### Core Characteristics
- Dynamic sizing
- Contiguous memory storage
- Fast random access
- Mutable length
#### Implementation Details
##### Structure
````java
public class ArrayList<T> {
    private T[] backingArray;    // Internal array to store elements
    private int size;            // Number of elements in the ArrayList
    public static final int INITIAL_CAPACITY = 9;
}
````
#### Core Operations & Time Complexities
##### Adding Elements
###### addToBack(T data)
````java
public void addToBack(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    addHelper(size, data);
}
````
-   Time Complexity: Amortized O(1)
-   Best for: Adding elements when order doesn't matter
-   Note: May trigger resizing of backing array
###### addToFront(T data)
````java
public void addToFront(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    addHelper(0, data);
}
````
-   Time Complexity: O(n)
-   Warning: Requires shifting all elements
-   Use Case: When elements must be added at the beginning
##### Internal Helper Method (Adding)

###### addHelper(int index, T data)
````java
@SuppressWarnings("unchecked")
private void addHelper(int index, T data) {
    // If array is full, create new array with double capacity
    if (size == backingArray.length) {
        T[] newArray = (T[]) new Object[backingArray.length * 2];
        int i;

        // Copy elements before index
        for (i = 0; i < index; i++) {
            newArray[i] = backingArray[i];
        }
        // Insert new element
        newArray[i] = data;
        // Copy remaining elements
        for (; i < size; i++) {
            newArray[i + 1] = backingArray[i];
        }

        backingArray = newArray;
    } else {
        // Shift elements to make room for new element
        for (int i = size; i > index; --i) {
            backingArray[i] = backingArray[i - 1];
        }
        backingArray[index] = data;
    }
    size++;
}
````

##### Removing Elements
###### removeFromBack()
````java
public T removeFromBack() {
    if (size == 0) {
        throw new java.util.NoSuchElementException("Cannot remove from an empty list");
    }
    return removeHelper(size - 1);
}
````
-   Time Complexity: O(1)
-   Most efficient removal operation
-   Checks for empty list
###### removeFromFront()
````java
public T removeFromFront() {
    if (size == 0) {
        throw new java.util.NoSuchElementException("Cannot remove from an empty list");
    }
    return removeHelper(0);
}
````
-   Time Complexity: O(n)
-   Requires shifting all elements
-   Use sparingly due to performance cost

###### removeAtIndex(int index)
```java
public T removeAtIndex(int index) {
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Index cannot be outside the "
            + "range [0, " + size + ")");
    }
    return removeHelper(index);
}
```
-   Time Complexity:
    -   Best Case (last element): O(1)
    -   Average/Worst Case: O(n)
-   Purpose: Removes and returns element at specified index
-   Validation: Checks for valid index range
-   Process:
    1.  Validates index bounds
    2.  Calls removeHelper for actual removal
    3.  Returns removed element

##### 🛠️ Internal Helper Method (Removing)
###### removeHelper(int index)

````java
private T removeHelper(int index) {
    T removed = backingArray[index];
    // Shift elements to fill the gap
    for (int i = index; i < size - 1; i++) {
        backingArray[i] = backingArray[i + 1];
    }
    backingArray[--size] = null;  // Clear last element and decrease size
    return removed;
}
````
-   Time Complexity: O(n)
-   Purpose: Internal method for handling element removal and shifting
-   Key Operations:
    1.  Element removal at specified index
    2.  Left-shifting remaining elements
    3.  Cleanup and size management

##### Access Operations
###### get(int index)
````java
public T get(int index) {
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Index cannot be outside the "
            + "range [0, " + size + ")");
    }
    return backingArray[index];
}
````
-   Time Complexity: O(1)
-   Direct index access
-   Bounds checking included

#### Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|-------|
| Add to Back | O(1)* | *Amortized |
| Add to Front | O(n) | Requires shifting |
| Add at Index | O(n) | Requires shifting |
| Remove from Back | O(1) | Most efficient removal |
| Remove from Front | O(n) | Requires shifting |
| Get/Set | O(1) | Direct access |
| Clear | O(1) | Memory reset |
| Size | O(1) | Constant tracking |

\* Amortized time complexity - occasional resizing operations are averaged over many operations

#### Best Practices
##### 1. Initialization
- State with reasonable initial capacity
- Consider expected size for optimal performance
##### 2. Usage Tips
````java
// Prefer adding to back when possible
list.addToBack(element);  // O(1)

// Avoid frequent front operations
list.addToFront(element); // O(n) - expensive!
````
##### 3. Memory Management
- Clear references when removing elements
- Reset to initial capacity when clearing

#### Common Use Cases
-   Dynamic lists of elements
-   Buffer implementation
-   Stack implementation
-   Collection management

#### Common Pitfalls
1. Frequent front operations
2. Not considering capacity growth
3. Not handling null elements
4. Ignoring bounds checking

#### When to Use ArrayList
- Need dynamic sizing
- Frequent random access
- Mostly back-end operations
- Memory locality is important
#### When Not to Use ArrayList
- Frequent insertions/deletions at front/middle
- Fixed size is sufficient
- Memory is extremely constrained
- Need concurrent access

#### References
https://youtu.be/PEnFFiQe1pM?si=KfpsngEBI0gesUbC
# Linked Lists

## Singly Linked List
A Singly Linked List is a fundamental data structure where elements are stored in nodes, each containing data and a reference to the next node in the sequence. Unlike arrays, linked lists don't require contiguous memory allocation, making them ideal for dynamic data management.

### Core Characteristics
-   Dynamic sizing (no fixed capacity)
-   Sequential access pattern
-   Node-based structure
-   Efficient insertions and deletions at known positions
-   Linear time search operations

### Implementation Details
#### Structure
````java
public class LinkedList<T> {
    private Node<T> head;
    private int size;
    
    private static class Node<T> {
        private T data;
        private Node<T> next;
        
        public Node(T data) {
            this.data = data;
            this.next = null;
        }
    }
}
````
#### Core Operations & Time Complexities
##### Adding Elements
###### addToFront(T data)
````java
public void addToFront(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    Node<T> newNode = new Node<>(data);
    newNode.next = head;
    head = newNode;
    size++;
}
````
-   Time Complexity: O(1)
-   Best for: Stack-like operations
-   Edge Cases:
    -   Null data
    -   First element (empty list)
###### addToBack(T data)
````java
public void addToBack(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    Node<T> newNode = new Node<>(data);
    
    if (head == null) {
        head = newNode;
    } else {
        Node<T> current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newNode;
    }
    size++;
}
````
-   Time Complexity: O(n)
-   Best for: Queue-like operations
-   Edge Cases:
    -   Null data
    -   Empty list
    -   Consider tracking tail pointer for O(1) operation
###### addAtIndex(int index, T data)
````java
public void addAtIndex(int index, T data) {
    if (index < 0 || index > size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    if (index == 0) {
        addToFront(data);
        return;
    }
    
    Node<T> current = head;
    for (int i = 0; i < index - 1; i++) {
        current = current.next;
    }
    
    Node<T> newNode = new Node<>(data);
    newNode.next = current.next;
    current.next = newNode;
    size++;
}
````
-   Time Complexity: O(n)
-   Best for: Ordered insertions
-   Edge Cases:
    -   Invalid index
    -   Null data
    -   Front insertion
##### Removing Elements
###### removeFromFront()
````java
public T removeFromFront() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    T data = head.data;
    head = head.next;
    size--;
    return data;
}
````
-   Time Complexity: O(1)
-   Best for: Stack operations
-   Edge Cases:
    -   Empty list
    -   Single element
###### removeFromBack()
````java
public T removeFromBack() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    if (size == 1) {
        T data = head.data;
        head = null;
        size--;
        return data;
    }
    
    Node<T> current = head;
    while (current.next.next != null) {
        current = current.next;
    }
    
    T data = current.next.data;
    current.next = null;
    size--;
    return data;
}
````
-   Time Complexity: O(n)
-   Best for: Queue operations
-   Edge Cases:
    -   Empty list
    -   Single element
    -   Consider tail pointer optimization
##### Access Operations
###### get(int index)
````java
public T get(int index) {
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    
    Node<T> current = head;
    for (int i = 0; i < index; i++) {
        current = current.next;
    }
    return current.data;
}
````
-   Time Complexity: O(n)
-   Best for: Sequential access
-   Edge Cases:
    -   Invalid index
    -   Empty list
#### Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Add to Front | O(1) | Constant time |
| Add to Back | O(n) | Linear traversal |
| Add at Index | O(n) | Traversal to index |
| Remove from Front | O(1) | Constant time |
| Remove from Back | O(n) | Linear traversal |
| Get | O(n) | Linear traversal |
| Size | O(1) | Tracked variable |

#### Best Practices
##### 1. Null Handling
````java
private void validateNotNull(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
}
````
##### 2. Index Validation
````java
private void validateIndex(int index, boolean isAdd) {
    int maxIndex = isAdd ? size : size - 1;
    if (index < 0 || index > maxIndex) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
}
````
##### 3. Memory Management
-   Clear references when removing nodes
-   Consider garbage collection implications
-   Track size for O(1) length checks
#### Common Pitfalls
#### 1. Losing References
````java
// WRONG - Lost reference to rest of list
head = new Node<>(data);  // Overwrites head reference

// CORRECT - Maintain list structure
Node<T> newNode = new Node<>(data);
newNode.next = head;
head = newNode;
````
#### 2. Not Handling Edge Cases
````java
// WRONG - Assumes non-empty list
head.next = newNode;

// CORRECT - Handle empty list
if (head == null) {
    head = newNode;
} else {
    head.next = newNode;
}
````

#### Reference
[Singly Linked List Video](https://youtu.be/-Yn5DU0_-lw?si=uyhzn4hUV9ZGr4zj)
## Doubly Linked List
A Doubly Linked List is a bidirectional linked data structure where each node contains data and references to both the next and previous nodes. This bidirectional linking enables efficient traversal in both directions and simplifies certain operations compared to singly linked lists.
#### Core Characteristics
-   Bi-directional traversal
-   Dynamic sizing
-   O(1) operations at both ends
-   Efficient insertions and deletions
-   Higher memory usage per node
#### Implementation Details
##### Structure
````java
public class DoublyLinkedList<T> {
    private Node<T> head;
    private Node<T> tail;
    private int size;
    
    private static class Node<T> {
        private T data;
        private Node<T> next;
        private Node<T> previous;
        
        Node(T data) {
            this.data = data;
            this.next = null;
            this.previous = null;
        }
        
        Node(T data, Node<T> previous, Node<T> next) {
            this.data = data;
            this.previous = previous;
            this.next = next;
        }
    }
}
````
#### Core Operations & Time Complexities
##### Adding Elements
###### addToFront(T data)
````java
public void addToFront(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    head = new Node<>(data, null, head);
    if (size == 0) {
        tail = head;  // First node is both head and tail
    } else {
        head.next.previous = head;  // Link old head back to new head
    }
    size++;
}
````
-   Time Complexity: O(1)
-   Best for: Stack-like operations, maintaining recent items
-   Edge Cases:
    -   Empty list
    -   Null data
    -   Maintaining tail reference
###### addToBack(T data)
````java
public void addToBack(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    Node<T> newNode = new Node<>(data, tail, null);
    if (size == 0) {
        head = newNode;
    } else {
        tail.next = newNode;
    }
    tail = newNode;
    size++;
}
````
-   Time Complexity: O(1)
-   Best for: Queue-like operations
-   Edge Cases:
    -   Empty list
    -   Null data
    -   Maintaining head reference
###### addAtIndex(int index, T data)
````java
public void addAtIndex(int index, T data) {
    if (index < 0 || index > size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    if (index == 0) {
        addToFront(data);
        return;
    }
    if (index == size) {
        addToBack(data);
        return;
    }
    
    // Choose optimal traversal direction
    Node<T> current;
    if (index < size / 2) {
        // Start from head
        current = head;
        for (int i = 0; i < index - 1; i++) {
            current = current.next;
        }
    } else {
        // Start from tail
        current = tail;
        for (int i = size - 1; i > index; i--) {
            current = current.previous;
        }
    }
    
    Node<T> newNode = new Node<>(data, current, current.next);
    current.next.previous = newNode;
    current.next = newNode;
    size++;
}
````
-   Time Complexity: O(n)
-   Optimization: Chooses optimal traversal direction
-   Edge Cases:
    -   Index bounds
    -   Null data
    -   Front/back insertions
##### Remove Elements
###### removeFromFront()
````java
public T removeFromFront() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    T data = head.data;
    head = head.next;
    size--;
    
    if (size == 0) {
        tail = null;
    } else {
        head.previous = null;
    }
    
    return data;
}
````
-   Time Complexity: O(1)
-   Best for: Stack operations
-  Edge Cases:
    -   Empty list
    -   Single element
    -   Maintaining tail reference
###### removeFromBack()
````java
public T removeFromBack() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    T data = tail.data;
    tail = tail.previous;
    size--;
    
    if (size == 0) {
        head = null;
    } else {
        tail.next = null;
    }
    
    return data;
}
````
-   Time Complexity: O(1)
-   Best for: Queue operations
-   Edge Cases:
    -   Empty list
    -   Single element
    -   Maintaining head reference
##### Access Operations
###### get(int index)
````java
public T get(int index) {
    if (index < 0 || index >= size) {
        throw new IndexOutOfBoundsException("Index: " + index + ", Size: " + size);
    }
    
    Node<T> current;
    if (index < size / 2) {
        current = head;
        for (int i = 0; i < index; i++) {
            current = current.next;
        }
    } else {
        current = tail;
        for (int i = size - 1; i > index; i--) {
            current = current.previous;
        }
    }
    return current.data;
}
````
-   Time Complexity: O(n)
-   Optimization: Bi-directional traversal
-   Edge Cases:
    -   Invalid index
    -   Empty list
### Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Add to Front | O(1) | Constant time |
| Add to Back | O(1) | Constant time with tail |
| Add at Index | O(n) | Optimal traversal direction |
| Remove from Front | O(1) | Constant time |
| Remove from Back | O(1) | Constant time with tail |
| Get | O(n) | Optimal traversal direction |
| Size | O(1) | Tracked variable |

#### Best Practices
##### 1. Bi-directional Link Maintenance
````java
// Always update both next and previous references
newNode.next = current.next;
newNode.previous = current;
current.next.previous = newNode;
current.next = newNode;
````
##### 2. Head/Tail Management
````java
// For single element
if (size == 1) {
    head = tail = null;
} else {
    // Update references appropriately
}
````
##### 3. Traversal Optimization
````java
// Choose optimal direction based on index
if (index < size / 2) {
    traverseFromHead();
} else {
    traverseFromTail();
}
````
#### Common Pitfalls
##### 1. Incomplete Link Updates
````java
// WRONG - Only updating one direction
current.next = newNode;

// CORRECT - Update both directions
current.next = newNode;
newNode.previous = current;
````
##### 2. Memory Leaks
````java
// WRONG - Leaving dangling references
head = head.next;

// CORRECT - Clear all references
T data = head.data;
Node<T> newHead = head.next;
head.next = null;  // Clear reference
if (newHead != null) {
    newHead.previous = null;
}
head = newHead;
````
##### References
[Doubly Linked List Video](https://youtu.be/m-8ZBO2ywaU?si=c7-K9iDSFlmzCuD0)

## Circular Singly Linked List

A Circular Singly Linked List is a variant of linked lists where the last node points back to the first node, creating a circle. This structure is particularly useful when I need continuous traversal or cyclic operations, like round-robin scheduling.

#### Core Characteristics
-  Last node connects to first node
-  Sequential access pattern
-  No null references
-   Continuous traversal capability
-   Efficient for cyclic operations
#### Implementation Details
##### Structure
````java
public class CircularLinkedList<T> {
    private Node<T> tail;  // Points to last node
    private int size;
    
    private static class Node<T> {
        T data;
        Node<T> next;
        
        Node(T data) {
            this.data = data;
            this.next = null;
        }
    }
}
````
💭 Why track tail instead of head?

-   O(1) insertions at both ends
-   Easy access to both first and last nodes
-   More efficient for common operations
#### Core Operations
##### Adding Elements
###### addingToFront(T data)
````java
public void addToFront(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    Node<T> newNode = new Node<>(data);
    if (isEmpty()) {
        newNode.next = newNode;  // Points to itself
        tail = newNode;
    } else {
        newNode.next = tail.next;  // Point to old first node
        tail.next = newNode;       // Update tail's next to new node
    }
    size++;
}
````
-   Time Complexity: O(1)
-   Important: Maintain circular nature
-   Edge Cases: Empty list handling
###### addToBack(T data)
````java
public void addToBack(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    Node<T> newNode = new Node<>(data);
    if (isEmpty()) {
        newNode.next = newNode;
    } else {
        newNode.next = tail.next;  // Point to first node
        tail.next = newNode;       // Update tail's next
    }
    tail = newNode;  // Update tail to new node
    size++;
}
````
-   Time Complexity: O(1)
-   Key Point: Tail reference makes this efficient
-   Edge Cases: Empty list, single element
##### Removing Elements
###### removeFromFront()
````java
public T removeFromFront() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    T data = tail.next.data;  // Get first node's data
    if (size == 1) {
        tail = null;
    } else {
        tail.next = tail.next.next;  // Skip first node
    }
    size--;
    return data;
}
````
-   Time Complexity: O(1)
-   Key Point: Maintain circular structure
-   Edge Cases: Empty list, single element
###### removeFromBack()
````java
public T removeFromBack() {
    if (isEmpty()) {
        throw new NoSuchElementException("List is empty");
    }
    
    T data = tail.data;
    if (size == 1) {
        tail = null;
    } else {
        Node<T> current = tail.next;
        while (current.next != tail) {
            current = current.next;
        }
        current.next = tail.next;
        tail = current;
    }
    size--;
    return data;
}
````
-   Time Complexity: O(n)
-   Note: Requires traversal to find second-to-last node
-   Edge Cases: Empty list, single element
##### Search Operation
````java
public boolean contains(T data) {
    if (isEmpty() || data == null) {
        return false;
    }
    
    Node<T> current = tail.next;  // Start at first node
    do {
        if (data.equals(current.data)) {
            return true;
        }
        current = current.next;
    } while (current != tail.next);
    
    return false;
}
````
-   Time Complexity: O(n)
-   Important: Use do-while for circular traversal
-   Handle: Null data, empty list
### 📊 Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Add to Front | O(1) | Constant time with tail reference |
| Add to Back | O(1) | Constant time with tail reference |
| Remove from Front | O(1) | Constant time operation |
| Remove from Back | O(n) | Requires traversal |
| Search | O(n) | Linear traversal |
| Size | O(1) | Tracked variable |

#### Best Practices
##### 1. Circular Reference Maintenance
````java
// Always ensure last node points to first
tail.next = tail.next.next;  // When removing
newNode.next = tail.next;    // When adding
````
##### 2. Empty List Handling
````java
if (isEmpty()) {
    // New node points to itself
    newNode.next = newNode;
    tail = newNode;
}
````
##### 3. Single Element Handling
````java
if (size == 1) {
    tail = null;  // For removal
    // OR
    tail = newNode;  // For insertion
}
````
#### Common Pitfalls
##### 1. Infinite Loops
````java
// WRONG - May loop forever
while (current.next != null) {  // Never true in circular list
    current = current.next;
}

// CORRECT
do {
    current = current.next;
} while (current != tail.next);
````
##### 2. Lost Circular Reference
````java
// WRONG - Loses circular structure
tail.next = newNode;

// CORRECT - Maintains circular structure
newNode.next = tail.next;
tail.next = newNode;
````

#### Reference
[Circular Linked List Playlist](https://youtube.com/playlist?list=PLBlnK6fEyqRjW4jK-CbshJuX20nc_3IaN&si=X7n0-QAF54ZSsf0_)

## Stack
#### Introduction
A Stack is a linear data structure that follows the LIFO (Last In First Out) principle. Like a stack of plates, elements are added and removed from the same end, called the top of the stack. This fundamental data structure is ideal for scenarios where we need strict order control over our operations.
#### Core Characteristics
-   LIFO (Last In, First Out) principle
-   Single point of access (top)
-   Dynamic sizing through array resizing
-   Ordered operations
-   Constant time operations (amortized)
#### Implementation Details
#### Structure
````java
public class Stack<T> {
    // Default capacity when no size is specified
    private static final int DEFAULT_CAPACITY = 10;
    
    // Internal array to store elements
    private T[] backingArray;
    
    // Keep track of the next available position
    private int size;
    
    // Constructor with default capacity
    @SuppressWarnings("unchecked")
    public Stack() {
        backingArray = (T[]) new Object[DEFAULT_CAPACITY];
        size = 0;
    }
    
    // Constructor with specified initial capacity
    @SuppressWarnings("unchecked")
    public Stack(int initialCapacity) {
        if (initialCapacity < 0) {
            throw new IllegalArgumentException("Initial capacity cannot be negative");
        }
        backingArray = (T[]) new Object[initialCapacity];
        size = 0;
    }
}
````

#### Core Operations
##### Push Operation
````java
public void push(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Cannot push null data");
    }
    
    // Check if we need to resize
    if (size == backingArray.length) {
        resize();
    }
    
    // Add element and increment size
    backingArray[size++] = data;
}

@SuppressWarnings("unchecked")
private void resize() {
    T[] newArray = (T[]) new Object[backingArray.length * 2];
    for (int i = 0; i < size; i++) {
        newArray[i] = backingArray[i];
    }
    backingArray = newArray;
}  
````
   Time Complexity: O(1) amortized
-   When to Use: Adding new elements to the stack
-   Key Points:
    -   Handles null check
    -   Automatic resizing
    -   Maintains LIFO order

##### Pop Operation
````java
public T pop() {
    if (isEmpty()) {
        throw new NoSuchElementException("Cannot pop from empty stack");
    }
    
    // Retrieve element and decrement size
    T data = backingArray[--size];
    backingArray[size] = null;  // Clear reference for garbage collection
    return data;
}
````
-   Time Complexity: O(1)
-   When to Use: Removing and retrieving the most recently added element
-   Key Points:
    -   Checks for empty stack
    -   Cleans up references
    -   Maintains LIFO order
##### Peek Operation
````java
public T peek() {
    if (isEmpty()) {
        throw new NoSuchElementException("Cannot peek empty stack");
    }
    return backingArray[size - 1];
}
````
-   Time Complexity: O(1)
-   When to Use: Viewing top element without removal
-   Key Points:
    -   No modification to stack
    -   Preserves state
    -   Checks for empty stack
#### Utility Operations
````java
// Check if stack is empty
public boolean isEmpty() {
    return size == 0;
}

// Get current number of elements
public int size() {
    return size;
}

// Clear all elements
@SuppressWarnings("unchecked")
public void clear() {
    backingArray = (T[]) new Object[DEFAULT_CAPACITY];
    size = 0;
}
````

#### 📊 Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Push | O(1)* | Amortized for resizing |
| Pop | O(1) | Constant time |
| Peek | O(1) | Constant time |
| isEmpty | O(1) | Constant time |
| Size | O(1) | Constant time |
| Clear | O(1) | New array allocation |

\* Amortized time complexity accounts for occasional resizing operations
#### Best Practices
##### 1. Memory Management
````java
// Always clear references when removing elements
public T pop() {
    T data = backingArray[--size];
    backingArray[size] = null;  // Clear reference
    return data;
}
````
##### 2. Capacity Handling
````java
// Consider shrinking array when usage is low
private void shrinkIfNeeded() {
    if (size > 0 && size < backingArray.length / 4) {
        resize(backingArray.length / 2);
    }
}
````
##### 3. Null Checking
````java
// Always validate input
public void push(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    // push implementation
}
````
#### Common Pitfalls
##### 1. Memory Leaks
````java
// WRONG - Memory leak
public T pop() {
    return backingArray[--size];  // Reference still held
}

// CORRECT - Clear reference
public T pop() {
    T data = backingArray[--size];
    backingArray[size] = null;  // Clear reference
    return data;
}
````
##### 2. Bound Checking
````java
// WRONG - No empty check
public T peek() {
    return backingArray[size - 1];  // Possible IndexOutOfBoundsException
}

// CORRECT - With empty check
public T peek() {
    if (isEmpty()) {
        throw new NoSuchElementException("Stack is empty");
    }
    return backingArray[size - 1];
}
````
#### Common Use Cases
##### 1. Function Call Stack
````java
Stack<FunctionCall> callStack = new Stack<>();
callStack.push(new FunctionCall("main"));
callStack.push(new FunctionCall("helper"));
// Current function is helper
callStack.pop();  // Return to main
````
##### 2. Expression Evaluation
````java
Stack<Character> parentheses = new Stack<>();
for (char c : expression.toCharArray()) {
    if (c == '(') {
        parentheses.push(c);
    } else if (c == ')') {
        if (!parentheses.isEmpty()) {
            parentheses.pop();
        } else {
            // Unmatched closing parenthesis
        }
    }
}
````
##### 3. Undo/Redo Operations
````java
Stack<Command> undoStack = new Stack<>();
Stack<Command> redoStack = new Stack<>();

void executeCommand(Command cmd) {
    cmd.execute();
    undoStack.push(cmd);
    redoStack.clear();  // Clear redo history
}
````

#### References
[Stack Introduction](https://youtu.be/L3ud3rXpIxA?si=m0pon3ja-WW28DON)
[Stack Implementation](https://youtu.be/RAMqDLI6_1c?si=OAPRPe-3-4nyqBCK)

TODO: Add LinkedStack implementation
## Queue
#### Introduction
A Queue is a linear data structure following the FIFO (First In, First Out) principle. Using a circular array implementation allows for efficient space usage and constant time operations by reusing array spaces that have been dequeued.
#### Core Characteristics
-   FIFO (First In, First Out) ordering
-   Circular array implementation
-   Dynamic sizing
-   Constant time operations (amortized)
-   Space efficient
#### Implementation Details
#### Structure
````java
public class Queue<T> {
    private T[] backingArray;
    private int front;      // Index of the front element
    private int size;       // Number of elements in queue
    private static final int INITIAL_CAPACITY = 10;
    
    @SuppressWarnings("unchecked")
    public Queue() {
        backingArray = (T[]) new Object[INITIAL_CAPACITY];
        front = 0;
        size = 0;
    }
}
````
#### Core Operations
##### Enqueue Operation
````java
public void enqueue(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Cannot enqueue null data");
    }
    
    // Check if we need to resize
    if (size == backingArray.length) {
        resize();
    }
    
    // Calculate rear index using modulo for circular behavior
    int rear = (front + size) % backingArray.length;
    backingArray[rear] = data;
    size++;
}

@SuppressWarnings("unchecked")
private void resize() {
    T[] newArray = (T[]) new Object[backingArray.length * 2];
    // Copy elements in order, starting from front
    for (int i = 0; i < size; i++) {
        newArray[i] = backingArray[(front + i) % backingArray.length];
    }
    backingArray = newArray;
    front = 0;  // Reset front to beginning of new array
}
````
-   Time Complexity: O(1) amortized
-   When to Use: Adding elements to queue
-   Key Points:
    -   Handles null check
    -   Circular indexing with modulo
    -   Resizes when full
##### Dequeue Operation
````java
public T dequeue() {
    if (isEmpty()) {
        throw new NoSuchElementException("Queue is empty");
    }
    
    T data = backingArray[front];
    backingArray[front] = null;  // Help GC
    front = (front + 1) % backingArray.length;
    size--;
    return data;
}
````
-   Time Complexity: O(1)
-   When to Use: Removing elements from front
-   Key Points:
    -   Handles empty queue
    -   Maintains circular structure
    -   Cleans up references
##### Peek Operation
````java
public T peek() {
    if (isEmpty()) {
        throw new NoSuchElementException("Queue is empty");
    }
    return backingArray[front];
}
````
-   Time Complexity: O(1)
-   When to Use: Examining front element
-   Key Points:
    -   No modification to queue
    -   Front element access
##### Utility Operations
````java
public boolean isEmpty() {
    return size == 0;
}

public int size() {
    return size;
}

@SuppressWarnings("unchecked")
public void clear() {
    backingArray = (T[]) new Object[INITIAL_CAPACITY];
    front = 0;
    size = 0;
}
````

#### Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Enqueue | O(1)* | Amortized for resizing |
| Dequeue | O(1) | Constant time |
| Peek | O(1) | Constant time |
| isEmpty | O(1) | Constant time |
| Size | O(1) | Constant time |
| Clear | O(1) | New array allocation |

\* Amortized time complexity accounts for occasional resizing operations
#### Best Practices
##### 1. Circular Index Calculation
````java
// Calculate next index with modulo
private int getNextIndex(int currentIndex) {
    return (currentIndex + 1) % backingArray.length;
}

// Calculate rear index
private int getRearIndex() {
    return (front + size) % backingArray.length;
}
````
##### 2. Resizing Strategy
````java
private void resize() {
    // Double size for amortized O(1)
    T[] newArray = (T[]) new Object[backingArray.length * 2];
    
    // Copy in order from front to rear
    for (int i = 0; i < size; i++) {
        newArray[i] = backingArray[(front + i) % backingArray.length];
    }
    front = 0;  // Reset front after resize
    backingArray = newArray;
}
````
##### 3. Memory Management
````java
public T dequeue() {
    T data = backingArray[front];
    backingArray[front] = null;  // Clear reference
    front = (front + 1) % backingArray.length;
    size--;
    return data;
}
````
#### Common Pitfalls
##### 1. Incorrect Circular Indexing
````java
// WRONG - May cause overflow
rear = rear + 1;
if (rear == backingArray.length) rear = 0;

// CORRECT - Use modulo
rear = (rear + 1) % backingArray.length;
````
##### 2. Resizing Issues
````java
// WRONG - Doesn't maintain order
System.arraycopy(backingArray, 0, newArray, 0, backingArray.length);

// CORRECT - Maintains order from front
for (int i = 0; i < size; i++) {
    newArray[i] = backingArray[(front + i) % backingArray.length];
}
````
#### Common Use Cases
##### 1. Task Scheduling
````java
Queue<Task> taskQueue = new Queue<>();
taskQueue.enqueue(new Task("Process payment"));
taskQueue.enqueue(new Task("Send email"));

while (!taskQueue.isEmpty()) {
    Task nextTask = taskQueue.dequeue();
    processTask(nextTask);
}
````
##### 2. BFS Implementation
````java
public void bfs(Node root) {
    Queue<Node> queue = new Queue<>();
    queue.enqueue(root);
    
    while (!queue.isEmpty()) {
        Node current = queue.dequeue();
        for (Node child : current.getChildren()) {
            queue.enqueue(child);
        }
    }
}
````
##### 3. Buffer Implementation
````java
public class Buffer<T> {
    private Queue<T> queue = new Queue<>();
    private final int capacity;
    
    public void write(T data) {
        if (queue.size() < capacity) {
            queue.enqueue(data);
        }
    }
    
    public T read() {
        return queue.isEmpty() ? null : queue.dequeue();
    }
}
````
#### References
[Queue Introduction](https://youtu.be/KxzhEQ-zpDc?si=kiGsG9eco3fsXaHR)
[Queue Implementation](https://youtu.be/EoisnPvUkOA?si=qoqVyM2dcjYFMrVa)

TODO: Add LinkedQueue Implementation
# 🌳 Tree-Based Structures
# 📊 Priority Queue
![Priority Queue](https://i.postimg.cc/7ZSt6tJw/temp-Imagez-FB1-Iv.avif)
### Introduction
A Priority Queue is an advanced queue that orders elements by their priority rather than insertion order. It's commonly implemented using a heap data structure, typically a min-heap or max-heap. In this implementation, we'll focus on a min-heap based priority queue where lower values have higher priority.
### Core Characteristics
-   📈 Priority-based ordering
-   🌳 Heap-based implementation
-   📏 Dynamic sizing
-   🔄 Self-balancing structure
-   ⚡ Logarithmic time operations
### Implementation Details
#### Structure
````java
public class PriorityQueue<T extends Comparable<? super T>> {
    // Initial capacity of the priority queue
    private static final int INITIAL_CAPACITY = 13;
    
    // Backing array for the heap
    private T[] backingArray;
    
    // Number of elements in the queue
    private int size;
    
    @SuppressWarnings("unchecked")
    public PriorityQueue() {
        backingArray = (T[]) new Comparable[INITIAL_CAPACITY];
        size = 0;
    }
}
````
### 🔧 Core Operations
#### Add Operation
````java
public void add(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Cannot add null data");
    }
    
    // Resize if necessary
    if (size + 1 == backingArray.length) {
        resize();
    }
    
    // Add element to the end and restore heap property
    backingArray[++size] = data;
    upHeap(size);
}

private void upHeap(int index) {
    while (index > 1 && 
           backingArray[index].compareTo(backingArray[index / 2]) < 0) {
        swap(backingArray, index, index / 2);
        index = index / 2;
    }
}
````
-   ⏱️ Time Complexity: O(log n)
-   💭 When to Use: Adding new elements with priority
-   ⚠️ Key Points:
    -   Maintains heap property
    -   Handles resizing
    -   Null checking
#### Remove Operation
````java
public T remove() {
    if (isEmpty()) {
        throw new NoSuchElementException("Queue is empty");
    }
    
    T removed = backingArray[1];
    backingArray[1] = backingArray[size];
    backingArray[size--] = null;
    
    if (!isEmpty()) {
        downHeap(1);
    }
    
    return removed;
}

private void downHeap(int index) {
    while (2 * index <= size) {
        int j = 2 * index;
        if (j < size && backingArray[j].compareTo(backingArray[j + 1]) > 0) {
            j++;
        }
        if (backingArray[index].compareTo(backingArray[j]) <= 0) {
            break;
        }
        swap(backingArray, index, j);
        index = j;
    }
}
````
-   ⏱️ Time Complexity: O(log n)
-   💭 When to Use: Removing highest priority element
-   ⚠️ Key Points:
    -   Maintains heap order
    -   Handles empty case
    -   Cleans references
#### Peek Operation
````java
public T peek() {
    if (isEmpty()) {
        throw new NoSuchElementException("Queue is empty");
    }
    return backingArray[1];
}
````
-   ⏱️ Time Complexity: O(1)
-   💭 When to Use: Viewing highest priority element
-   ⚠️ Key Points:
    -   No modification to structure
    -   Empty check
### 📊 Performance Summary
## 📊 Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Add/Offer | O(log n) | Requires upheap |
| Remove/Poll | O(log n) | Requires downheap |
| Peek | O(1) | Constant time |
| isEmpty | O(1) | Constant time |
| Size | O(1) | Constant time |
| Clear | O(1) | New array allocation |
### 💡 Best Practices
#### 1. Maintain Heap Property
````java
private void swap(T[] arr, int i, int j) {
    T temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}

private int parent(int index) {
    return index / 2;
}

private int leftChild(int index) {
    return 2 * index;
}

private int rightChild(int index) {
    return 2 * index + 1;
}
````
#### 2. Efficient Resizing
````java
@SuppressWarnings("unchecked")
private void resize() {
    T[] newArray = (T[]) new Comparable[backingArray.length * 2];
    for (int i = 1; i <= size; i++) {
        newArray[i] = backingArray[i];
    }
    backingArray = newArray;
}
````
#### 3. Handle Special Cases
````java
public boolean isEmpty() {
    return size == 0;
}

@SuppressWarnings("unchecked")
public void clear() {
    backingArray = (T[]) new Comparable[INITIAL_CAPACITY];
    size = 0;
}
````
### ⚠️ Common Pitfalls
#### 1. Index Management
````java
// WRONG - Using 0-based indexing
private int parent(int i) {
    return (i - 1) / 2;
}

// CORRECT - Using 1-based indexing
private int parent(int i) {
    return i / 2;
}
````
#### 2. Comparator Consistency
````java
// WRONG - Inconsistent comparison
if (a.someValue() < b.someValue()) {
    swap(a, b);
}

// CORRECT - Use compareTo
if (a.compareTo(b) < 0) {
    swap(a, b);
}
````
### 🎯 Common Use Cases
#### 1. Task Scheduling
````java
class Task implements Comparable<Task> {
    private int priority;
    private String description;
    
    @Override
    public int compareTo(Task other) {
        return Integer.compare(this.priority, other.priority);
    }
}

PriorityQueue<Task> taskQueue = new PriorityQueue<>();
taskQueue.add(new Task(1, "High Priority"));
taskQueue.add(new Task(3, "Low Priority"));
````
#### 2. Dijkstra's Algorithm
````java
PriorityQueue<Node> pq = new PriorityQueue<>((a, b) -> 
    Integer.compare(a.distance, b.distance));
pq.add(source);
while (!pq.isEmpty()) {
    Node current = pq.remove();
    // Process node
}
````
#### 3. Event Processing
````java
class Event implements Comparable<Event> {
    private long timestamp;
    
    @Override
    public int compareTo(Event other) {
        return Long.compare(this.timestamp, other.timestamp);
    }
}

PriorityQueue<Event> events = new PriorityQueue<>();
events.add(new Event(System.currentTimeMillis()));
````

### References
[Priority Queue Introduction](https://youtu.be/wptevk0bshY?si=620-DcPMa14F0lL5)
[Priority Queue Min Heaps and Max Heaps](https://youtu.be/HCEr35qpawQ?si=V1_BJIdDTXqDzI3z)
[Priority Queue Adding Elements](https://youtu.be/QOJ-CmQiXko?si=MJCRzTB1yDV0qfcF)
[Priority Queue Removing Elements](https://youtu.be/eVq8CmoC1x8?si=S9Lrx5MllIeqzrT-)

# 🌳 Binary Tree
![Binary Tree Router](https://i.postimg.cc/52SBdTL6/temp-Image-B78xzp.avif)

### Introduction
A Binary Tree is a hierarchical, non-linear data structure where each node has at most two children, referred to as left child and right child. Unlike arrays or linked lists that store data sequentially, Binary Trees allow for representing hierarchical relationships between elements.

### Core Characteristics
-   🌿 Each node has at most two children
-   🔝 Single root node
-   📊 Hierarchical structure
-   🔄 Recursive nature
-   🎯 Multiple traversal options

### Implementation Details
#### Structure
````java
public class BinaryTree<T> {
    private Node<T> root;
    private int size;
    
    private static class Node<T> {
        T data;
        Node<T> left;
        Node<T> right;
        
        Node(T data) {
            this.data = data;
            this.left = null;
            this.right = null;
        }
    }
    
    public BinaryTree() {
        root = null;
        size = 0;
    }
}
````
### 🔧 Core Operations
#### Traversal Operations
````java
// InOrder Traversal (Left, Root, Right)
public void inOrderTraversal(Node<T> node) {
    if (node != null) {
        inOrderTraversal(node.left);
        process(node.data);
        inOrderTraversal(node.right);
    }
}

// PreOrder Traversal (Root, Left, Right)
public void preOrderTraversal(Node<T> node) {
    if (node != null) {
        process(node.data);
        preOrderTraversal(node.left);
        preOrderTraversal(node.right);
    }
}

// PostOrder Traversal (Left, Right, Root)
public void postOrderTraversal(Node<T> node) {
    if (node != null) {
        postOrderTraversal(node.left);
        postOrderTraversal(node.right);
        process(node.data);
    }
}

// Level Order Traversal (BFS)
public void levelOrderTraversal() {
    if (root == null) return;
    
    Queue<Node<T>> queue = new LinkedList<>();
    queue.offer(root);
    
    while (!queue.isEmpty()) {
        Node<T> current = queue.poll();
        process(current.data);
        
        if (current.left != null) queue.offer(current.left);
        if (current.right != null) queue.offer(current.right);
    }
}
````
-   ⏱️ Time Complexity: O(n) for all traversals
-   💭 When to Use: Different traversal orders for different needs
-   ⚠️ Key Points: Each traversal visits all nodes exactly once

#### Insertion Operation
````java
public void insert(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    if (root == null) {
        root = new Node<>(data);
        size++;
        return;
    }
    
    // Level-order insertion
    Queue<Node<T>> queue = new LinkedList<>();
    queue.offer(root);
    
    while (!queue.isEmpty()) {
        Node<T> current = queue.poll();
        
        if (current.left == null) {
            current.left = new Node<>(data);
            size++;
            return;
        } else {
            queue.offer(current.left);
        }
        
        if (current.right == null) {
            current.right = new Node<>(data);
            size++;
            return;
        } else {
            queue.offer(current.right);
        }
    }
}
````

-   ⏱️ Time Complexity: O(n)
-   💭 When to Use: Adding new nodes to the tree
-   ⚠️ Key Points: Level-order insertion maintains tree balance

#### Search Operation
````java
public boolean contains(T data) {
    return searchHelper(root, data);
}

private boolean searchHelper(Node<T> node, T data) {
    if (node == null) return false;
    
    if (node.data.equals(data)) return true;
    
    return searchHelper(node.left, data) || 
           searchHelper(node.right, data);
}
````
-   ⏱️ Time Complexity: O(n)
-   💭 When to Use: Finding elements in the tree
-   ⚠️ Key Points: Must traverse potentially entire tree

### 📊 Performance Summary
## 📊 Performance Summary

| Operation | Time Complexity | Notes |
|-----------|----------------|--------|
| Insertion | O(n) | Level-order insertion |
| Search | O(n) | Worst case traversal |
| Deletion | O(n) | Find and reorganize |
| Traversal | O(n) | All traversal types |
| Height | O(n) | Must visit all nodes |
| Size | O(1) | Maintained variable |
| isEmpty | O(1) | Check root null |

### 💡 Best Practices
#### 1. Proper Node Handling
````java
private void validate(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
}
````
#### 2. Traversal Selection
````java
// Use appropriate traversal for the task
// InOrder: Sorted sequence in BST
// PreOrder: Copy/serialize tree
// PostOrder: Delete tree/calculate size
// LevelOrder: Level-based processing
````
#### 3. Memory Management
````java
public void clear() {
    root = null;  // Allow GC to clean up
    size = 0;
}
````

### ⚠️ Common Pitfalls
#### 1. Not Handling Null Cases
````java
// WRONG
public void process(Node<T> node) {
    process(node.left);  // NPE if node is null
}  
 
// CORRECT
public void process(Node<T> node) {
    if (node == null) return;
    process(node.left);
}
````

#### 2. Improper Traversal Choice
````java
// WRONG - Using inOrder for level-based processing
// CORRECT - Use levelOrder for level-based operations
public void printLevelByLevel() {
    levelOrderTraversal();
}
````

### 🎯 Common Use Cases
#### 1. File System Representation
````java
class FileNode<T> extends Node<T> {
    boolean isDirectory;
    // File system specific operations
}
````
#### 2. Expression Trees
````java
class ExpressionNode<T> extends Node<T> {
    boolean isOperator;
    public double evaluate() {
        // Evaluation logic
    }
}
````
#### 3. Decision Trees
````java
class DecisionNode<T> extends Node<T> {
    boolean isLeaf;
    public T decide(Input input) {
        // Decision logic
    }
}
````

### References
[Binary Tree Data Structure](https://youtu.be/H5JubkIy_p8?si=0SZXcikEuU6108b1)

# 🌳 Binary Search Tree
![Binary Search Tree](https://i.postimg.cc/sDrLyFbr/temp-Image-Tazx-Mr.avif)

### Introduction

A Binary Search Tree (BST) is a binary tree that maintains an ordering property: for each node, all elements in its left subtree are less than the node's value, and all elements in its right subtree are greater. This property makes BSTs efficient for searching, inserting, and deleting elements.

### Core Characteristics
-   📊 Ordered structure
-   🔍 Efficient searching
-   🎯 Dynamic operations
-   🌿 Binary tree properties
-   ⚖️ Balance affects performance

### Implementation Details
#### Structure
````java
public class BST<T extends Comparable<? super T>> {
    private BSTNode<T> root;
    private int size;
    
    private static class BSTNode<T> {
        T data;
        BSTNode<T> left;
        BSTNode<T> right;
        
        BSTNode(T data) {
            this.data = data;
            left = null;
            right = null;
        }
    }
}
````

### 🔧 Core Operations
#### Add Operation
````java
public void add(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    root = addHelper(data, root);
}

private BSTNode<T> addHelper(T data, BSTNode<T> node) {
    if (node == null) {
        size++;
        return new BSTNode<>(data);
    }
    
    int compare = data.compareTo(node.data);
    if (compare < 0) {
        node.left = addHelper(data, node.left);
    } else if (compare > 0) {
        node.right = addHelper(data, node.right);
    }
    return node;
}
````
-   ⏱️ Time Complexity: O(log n) average, O(n) worst case
-   💭 When to Use: Inserting new elements while maintaining order
-   ⚠️ Key Points:
    -   Maintains BST property
    -   Handles duplicates
    -   Recursive implementation

#### Remove Operation
````java
public T remove(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    BSTNode<T> dummy = new BSTNode<>(null);
    root = removeHelper(data, root, dummy);
    return dummy.data;
}

private BSTNode<T> removeHelper(T data, BSTNode<T> node, BSTNode<T> dummy) {
    if (node == null) {
        throw new NoSuchElementException("Data not found");
    }
    
    int compare = data.compareTo(node.data);
    if (compare < 0) {
        node.left = removeHelper(data, node.left, dummy);
    } else if (compare > 0) {
        node.right = removeHelper(data, node.right, dummy);
    } else {
        dummy.data = node.data;
        size--;
        
        if (node.left == null) {
            return node.right;
        } else if (node.right == null) {
            return node.left;
        } else {
            BSTNode<T> successor = findSuccessor(node.right);
            node.data = successor.data;
            node.right = removeHelper(successor.data, node.right, dummy);
        }
    }
    return node;
}
````
-   ⏱️ Time Complexity: O(log n) average, O(n) worst case
-   💭 When to Use: Removing elements while maintaining order
-   ⚠️ Key Points:
    -   Three cases: leaf, one child, two children
    -   Uses successor for two-child case
    -   Maintains BST property

#### Search Operation
````java
public T get(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    
    BSTNode<T> node = getHelper(data, root);
    if (node == null) {
        throw new NoSuchElementException("Data not found");
    }
    return node.data;
}

private BSTNode<T> getHelper(T data, BSTNode<T> node) {
    if (node == null) {
        return null;
    }
    
    int compare = data.compareTo(node.data);
    if (compare < 0) {
        return getHelper(data, node.left);
    } else if (compare > 0) {
        return getHelper(data, node.right);
    }
    return node;
}
````
-   ⏱️ Time Complexity: O(log n) average, O(n) worst case
-   💭 When to Use: Finding elements in the tree
-   ⚠️ Key Points:
    -   Uses comparisons for direction
    -   Returns stored data
    -   Handles not found case

### Traversal Operations
````java
// In-order traversal (sorted order)
public List<T> inorder() {
    List<T> result = new ArrayList<>();
    inorderHelper(root, result);
    return result;
}

private void inorderHelper(BSTNode<T> node, List<T> result) {
    if (node != null) {
        inorderHelper(node.left, result);
        result.add(node.data);
        inorderHelper(node.right, result);
    }
}
````
-   ⏱️ Time Complexity: O(n)
-   💭 When to Use: Getting elements in sorted order
-   ⚠️ Key Points:
    -   In-order gives sorted sequence
    -   Pre-order for copying tree
    -   Post-order for deletion

## 📊 Performance Summary

| Operation | Average Case | Worst Case | Notes |
|-----------|--------------|------------|--------|
| Insert | O(log n) | O(n) | Unbalanced case |
| Remove | O(log n) | O(n) | Unbalanced case |
| Search | O(log n) | O(n) | Unbalanced case |
| Traversal | O(n) | O(n) | Visits all nodes |
| Height | O(1) | O(1) | Cached value |
| Size | O(1) | O(1) | Maintained count |

### 💡 Best Practices
#### 1. Balance Maintenance
````jav
// Consider using self-balancing variants for better performance guarantees
// AVL or Red-Black trees for automatic balancing
````
#### 2. Comparison Handling
````java
// Use compareTo consistently
int compare = data.compareTo(node.data);
if (compare < 0) {
    // Go left
} else if (compare > 0) {
    // Go right
}
````
#### 3. Null Handling
````java
// Always validate input
if (data == null) {
    throw new IllegalArgumentException("Data cannot be null");
}
````

### ⚠️ Common Pitfalls
#### 1. Unbalanced Trees
````java
// WRONG - Adding sorted data creates linear structure
bst.add(1);
bst.add(2);
bst.add(3);  // Creates right-skewed tree

// BETTER - Balance the tree or use self-balancing variant
````
#### 2. Memory Management
````java
// WRONG - Memory leak in remove
node = null;  // Only removes reference

// CORRECT - Clean all references
node.left = null;
node.right = null;
node.data = null;
node = null;
````

### 🎯 Common Use Cases
#### 1. Dictionary Implementation
````java
BST<String> dictionary = new BST<>();
dictionary.add("apple");
dictionary.add("banana");
// Fast lookups: O(log n) average
````
#### 2. Priority Management
````java
BST<Task> tasks = new BST<>();
tasks.add(new Task(1, "High Priority"));
tasks.add(new Task(2, "Medium Priority"));
// Natural ordering of tasks
````
#### 3. Symbol Tables
````java
BST<Symbol> symbolTable = new BST<>();
symbolTable.add(new Symbol("x", 10));
symbolTable.add(new Symbol("y", 20));
// Efficient symbol lookup
````

### References
[Binary Search Trees](https://youtu.be/pYT9F8_LFTM?si=llySEAWqBX3jJ_tN)
[Binary Search Tree Introduction](https://youtu.be/JfSdGQdAzq8?si=EKKPhNxENwZlQWNB)
[Binary Search Tree Insertion](https://youtu.be/LwpLXm3eb6A?si=xvpTFxTCcW1JY55R)
[Binary Search Tree Removal](https://youtu.be/8K7EO7s_iFE?si=cm7yYT1m76rhtzLn)
[Binary Search Tree Traversal](https://youtu.be/k7GkEbECZK0?si=ULXRc1mnU2cfijtM)

# 🌲 Advanced Tree-Based Structures
# 🌳 AVL Trees
![AVL Tree](https://i.postimg.cc/ZKHM6RMf/temp-Image-Ie-Nfq-P.avif)

An AVL Tree is a self-balancing bin tree where the heights of the left and right subtrees of any node differ by at most one. This balance ot ensures that the tree remains approximately balanced during insertion deletions, maintaining O(log n) time complexity for all operations.

### Core Characteristics
-   🔄 Self-balancing mechanism
-   📏 Height tracking
-   ⚖️ Balance factor management
-   🎯 BST properties maintained
-   🔍 Guaranteed O(log n) operations

### Implementation Details
#### Structure

````java
public class AVLTree<T extends Comparable<? super T>> {
     AVLNode<T> root;
    private int size;
    
    private static class AVLNode<T> {
     T data;
        AVLNode<T> left;
     AVLNode<T> right;
     int height;
     int balanceFactor;
            AVLNode(T data) {
            this.data = data;
            this.height = 0;
            this.balanceFactor = 0;
        }
    }
}
````

### Node Properties

1.  `data`: Stores the actual value/element
2.  `left`: Reference to left child n lement etil ri clrenco right child node
3.  `height`: Distance to the furthest leaf in its subtree
4.  `balanceFactor`: Difference between left and right subtree heights

### 🔧 Core Operations
Balance Helper Methods
````java
private int height(AVLNode<T> node) {
    return node == null ? -1 : node.height;
}

private void updateHeightAndBF(AVLNode<T> node) {
    int leftHeight = height(node.left);
    int rightHeight = height(node.right);
    node.height = Math.max(leftHeight, rightHeight) + 1;
    node.balanceFactor = leftHeight - rightHeight;
}
````
-   ⏱️ Time Complexity: O(1)
-   💭 When to Use: After any structural changes
-   ⚠️ Key Points:
    -   Height of null node is -1
    -   Balance factor = leftHeight - rightHeight
    -   Must update after rotations

#### Rotation Operations
````java
private AVLNode<T> rotateLeft(AVLNode<T> node) {
    AVLNode<T> newRoot = node.right;
    node.right = newRoot.left;
    newRoot.left = node;
    
    updateHeightAndBF(node);
    updateHeightAndBF(newRoot);
    return newRoot;
}

private AVLNode<T> rotateRight(AVLNode<T> node) {
    AVLNode<T> newRoot = node.left;
    node.left = newRoot.right;
    newRoot.right = node;
    
    updateHeightAndBF(node);
    updateHeightAndBF(newRoot);
    return newRoot;
}
````
-   ⏱️ Time Complexity: O(1)
-   💭 When to Use: Rebalancing after insertions/deletions
-   ⚠️ Key Points:
    -   Update heights after rotation
    -   Maintain BST properties
    -   Return new root of subtree
#### Balance Operation
````java
private AVLNode<T> balance(AVLNode<T> node) {
    updateHeightAndBF(node);
    
    if (node.balanceFactor < -1) {  // Right heavy
        if (node.right.balanceFactor > 0) {  // Right-Left case
            node.right = rotateRight(node.right);
        }
        return rotateLeft(node);
    } else if (node.balanceFactor > 1) {  // Left heavy
        if (node.left.balanceFactor < 0) {  // Left-Right case
            node.left = rotateLeft(node.left);
        }
        return rotateRight(node);
    }
    
    return node;
}
````
-   ⏱️ Time Complexity: O(1)
-   💭 When to Use: After modifications that might affect balance
-   ⚠️ Key Points:
    -   Handles all four rotation cases
    -   Updates height before checking balance
    -   Returns balanced subtree root

#### Add Operation
````java
public void add(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Data cannot be null");
    }
    root = addHelper(data, root);
}

private AVLNode<T> addHelper(T data, AVLNode<T> node) {
    if (node == null) {
        size++;
        return new AVLNode<>(data);
    }
    
    int compare = data.compareTo(node.data);
    if (compare < 0) {
        node.left = addHelper(data, node.left);
    } else if (compare > 0) {
        node.right = addHelper(data, node.right);
    }
    
    return balance(node);
}
````
-   ⏱️ Time Complexity: O(log n)
-   💭 When to Use: Adding new elements
-   ⚠️ Key Points:
    -   BST properties maintained
    -   Auto-balancing after insertion
    -   Uses pointer reinforcement

### 📊 Performance Summary
| Operation | Average Case | Worst Case | Notes |
|-----------|--------------|------------|--------|
| Add | O(log n) | O(log n) | Includes rebalancing |
| Remove | O(log n) | O(log n) | Includes rebalancing |
| Search | O(log n) | O(log n) | Same as BST |
| Rotation | O(1) | O(1) | Height updates included |
| Balance | O(1) | O(1) | Maximum two rotations |
| Height | O(1) | O(1) | Cached in node |

### 🎯 Visualization of Rotations
#### Left Rotation
````
Before:       After:
  A            B
   \          / \
    B   =>   A   C
     \
      C
````

#### Right Rotation
````
Before:       After:
    C          B
   /          / \
  B    =>    A   C
 /
A
````

#### Double Rotation (Left-Right)
````
Before:       Middle:        After:
  C            C              B
 /            /             /  \
A     =>     B     =>     A    C
 \          /
  B        A
````

#### Double Rotation (Right-Left)
````
Before:         Middle:         After:
    A             A               B
     \             \            /  \
      C     =>      B    =>    A    C
     /               \
    B                 C
````

### 💡 Best Practices
#### 1. Height Management
````java
// Always update heights bottom-up
updateHeightAndBF(node);
if (node.parent != null) {
    updateHeightAndBF(node.parent);
}
````

#### 2. Balance Factor Checks
````java
// Check both balance factor and height
if (Math.abs(node.balanceFactor) > 1) {
    return balance(node);
}
````

#### 3. Rotation Selection
````java
// Clear conditions for rotation type
if (node.balanceFactor > 1) {  // Left heavy
    if (node.left.balanceFactor < 0) {  // Left-Right case
        node.left = rotateLeft(node.left);
    }
    return rotateRight(node);
}
````

### ⚠️ Common Pitfalls
#### 1. Incorrect Height Updates
````java
// WRONG - Not updating ancestor heights
node = balance(node);

// CORRECT - Update all affected nodes
node = balance(node);
updateAncestorHeights(node);
````
#### 2. Balance Factor Calculation
````java
// WRONG - Swapped height difference
balanceFactor = rightHeight - leftHeight;

// CORRECT
balanceFactor = leftHeight - rightHeight;
````

### References
[AVL Trees Simply Explained](https://youtu.be/zP2xbKerIds?si=OQI-Kxgsr9iQKsy-)
[Red-Black Trees in 4 min](https://youtu.be/qvZGUFHWChY?si=zfLMb0HG7IFSS5gC)
[2-3 Trees](https://youtu.be/tPoG8XcnPO0?si=UFsoKQnf9dco_rsX)
[K-D Trees](https://youtu.be/BK5x7IUTIyU?si=8ityNI3gyNnkO68f)
[M-Ary Trees](https://en.wikipedia.org/wiki/M-ary_tree)

# 🎯 Hash-Based Structures
# #️⃣ HashMaps
![HashMap](https://i.postimg.cc/YCcYzBTV/temp-Image-TBGZv5.avif)

A HashMap is a data structure that implements the Map ADT, storing key-value pairs for O(1) average-case access time. This implementation uses separate chaining for collision resolution, where collisions are handled by maintaining linked lists at each array index.

### Core Characteristics
-   🔑  **Unique Key Mapping**
    -   Each key can map to only one value
    -   Keys must be immutable
    -   Values can be modified or duplicated
    -   Perfect for one-to-one relationships
-   ⚡  **Constant-Time Operations**
    -   O(1) average case for insertions
    -   O(1) average case for retrievals
    -   O(1) average case for deletions
    -   Performance dependent on hash function quality
-   🎯  **Hash Distribution**
    -   Converts keys to array indices via hashing
    -   Uses hashCode() method for initial hash
    -   Compresses hash to fit array bounds
    -   Aims for uniform distribution of keys
-   ⛓️  **Collision Management**
    -   Handles key collisions using linked lists
    -   Each array index can store multiple entries
    -   Entries in same bucket form a chain
    -   Search within chain is O(n) worst case
-   ⚖️  **Load Factor Control**
    -   Maintains ratio of size to capacity
    -   Typically keeps load factor below 0.67
    -   Triggers resizing when threshold reached
    -   Prevents performance degradation
    -   Uses prime number capacities for better distribution
-   🔄  **Dynamic Resizing**
    -   Doubles capacity when load factor exceeded
    -   Adds 1 to ensure prime capacity
    -   Rehashes all existing entries
    -   Maintains performance characteristics

### Implementation Details
#### Node Structure
````java
private static class Node<K, V> {
    K key;
    V value;
    Node<K, V> next;
    
    Node(K key, V value) {
        this.key = key;
        this.value = value;
        this.next = null;
    }
}
````
### Basic Class Structure
````java
public class HashMap<K, V> {
    private Node<K, V>[] table;
    private int size;
    private static final int INITIAL_CAPACITY = 13;  // Prime number
    private static final double MAX_LOAD_FACTOR = 0.67;
    
    @SuppressWarnings("unchecked")
    public HashMap() {
        table = (Node<K, V>[]) new Node[INITIAL_CAPACITY];
        size = 0;
    }
}
````
### Core Operations
#### Put Operation
````java
public V put(K key, V value) {
    if (key == null) {
        throw new IllegalArgumentException("Key cannot be null");
    }
    
    // Check if resize is needed
    if ((double) (size + 1) / table.length > MAX_LOAD_FACTOR) {
        resize();
    }
    
    int index = getIndex(key);
    
    // Check if key already exists
    Node<K, V> current = table[index];
    while (current != null) {
        if (current.key.equals(key)) {
            V oldValue = current.value;
            current.value = value;
            return oldValue;
        }
        current = current.next;
    }
    
    // Add new node at the beginning of the chain
    Node<K, V> newNode = new Node<>(key, value);
    newNode.next = table[index];
    table[index] = newNode;
    size++;
    
    return null;
}

private int getIndex(K key) {
    return Math.abs(key.hashCode() % table.length);
}
````

#### Get Operation
````java
public V get(K key) {
    if (key == null) {
        throw new IllegalArgumentException("Key cannot be null");
    }
    
    int index = getIndex(key);
    Node<K, V> current = table[index];
    
    while (current != null) {
        if (current.key.equals(key)) {
            return current.value;
        }
        current = current.next;
    }
    
    return null;
}
````

#### Remove Operation
````java
public V remove(K key) {
    if (key == null) {
        throw new IllegalArgumentException("Key cannot be null");
    }
    
    int index = getIndex(key);
    Node<K, V> current = table[index];
    Node<K, V> prev = null;
    
    while (current != null) {
        if (current.key.equals(key)) {
            if (prev == null) {
                table[index] = current.next;
            } else {
                prev.next = current.next;
            }
            size--;
            return current.value;
        }
        prev = current;
        current = current.next;
    }
    
    return null;
}
````

#### Resize Operation
````java
@SuppressWarnings("unchecked")
private void resize() {
    int newCapacity = (2 * table.length) + 1;  // Prime number
    Node<K, V>[] oldTable = table;
    table = (Node<K, V>[]) new Node[newCapacity];
    size = 0;
    
    // Rehash all existing entries
    for (Node<K, V> head : oldTable) {
        Node<K, V> current = head;
        while (current != null) {
            put(current.key, current.value);
            current = current.next;
        }
    }
}
````

### Performance Characteristics
| Operation | Average Case | Worst Case | Notes |
|-----------|--------------|------------|--------|
| Put | O(1) | O(n) | When chain degrades to linked list |
| Get | O(1) | O(n) | When chain degrades to linked list |
| Remove | O(1) | O(n) | When chain degrades to linked list |
| Space | O(n) | O(n) | n = number of key-value pairs |

### 💡 Best Practices
#### 1. Load Factor Management
````java
private boolean needsResize() {
    return (double) size / table.length > MAX_LOAD_FACTOR;
}
````

#### 2. Key Quality
````java
// Override hashCode() in key objects
@Override
public int hashCode() {
    int hash = 17;
    hash = 31 * hash + field1.hashCode();
    hash = 31 * hash + field2.hashCode();
    return hash;
}
````

#### 3. Proper Equals Implementation
````java
@Override
public boolean equals(Object obj) {
    if (this == obj) return true;
    if (obj == null || getClass() != obj.getClass()) return false;
    MyKey other = (MyKey) obj;
    return field1.equals(other.field1) && field2.equals(other.field2);
}
````

###  ⚠️ Common Pitfalls
#### 1. Poor Hash Distribution
````java
// WRONG: Poor hash function
public int hashCode() {
    return 1;  // All items hash to same bucket
}

// BETTER: Good distribution
public int hashCode() {
    return Objects.hash(field1, field2);
}
````

#### 2. Missing Null Checks
````java
// WRONG: No null check
public V put(K key, V value) {
    int index = key.hashCode() % table.length;  // NullPointerException!
    
// CORRECT: With null check
public V put(K key, V value) {
    if (key == null) {
        throw new IllegalArgumentException("Key cannot be null");
    }
    int index = getIndex(key);
````

HashMaps provide efficient key-value storage with constant-time average case operations, making them ideal for lookup-intensive applications. The separate chaining implementation offers a good balance between simplicity and performance.

### References
[HashTables with Collision Management](https://youtube.com/playlist?list=PLDV1Zeh2NRsDH5Wq-Vk5tDb8gH03cULZS&si=gXITqecXbB73ARdC)

# 🕸️ Graph-Based Structures
![Directed Graph](https://i.postimg.cc/WbQbHMmY/temp-Imagen2z-WHZ.avif)
A Graph is a data structure that models relationships between elements using vertices (nodes) and edges. This implementation represents a directed graph using vertex and edge sets along with an adjacency list representation for efficient neighbor access.

### Core Characteristics
-   🔍  **Vertex Management**
    -   Each vertex contains generic typed data
    -   Vertices are unique based on data equality
    -   Supports null-safe vertex operations
    -   Maintains a vertex set for O(1) lookups
-   🔗  **Edge Properties**
    -   Directed edges from vertex u to v
    -   Weighted connections
    -   Maintains edge set for global access
    -   Supports undirected graphs via bidirectional edges
-   📊  **Adjacency Structure**
    -   Maps vertices to neighbor lists
    -   Includes edge weights in adjacency entries
    -   Efficient neighbor access
    -   Space-efficient for sparse graphs

### Implementation Details
#### Vertex Class
````java
public class Vertex<T> {
    private T data;
    
    public Vertex(T data) {
        if (data == null) {
            throw new IllegalArgumentException("Data cannot be null.");
        }
        this.data = data;
    }
    
    public T getData() {
        return data;
    }
    
    @Override
    public boolean equals(Object o) {
        if (o != null && o instanceof Vertex) {
            return data.equals(((Vertex<?>) o).data);
        }
        return false;
    }
    
    @Override
    public int hashCode() {
        return data.hashCode();
    }
}
````

#### Edge Class
````java
public class Edge<T> implements Comparable<Edge<? super T>> {
    private Vertex<T> u;  // Source vertex
    private Vertex<T> v;  // Destination vertex
    private int weight;   // Edge weight
    
    public Edge(Vertex<T> u, Vertex<T> v, int weight) {
        if (u == null || v == null) {
            throw new IllegalArgumentException("Arguments cannot be null.");
        }
        this.u = u;
        this.v = v;
        this.weight = weight;
    }
    
    public Vertex<T> getU() { return u; }
    public Vertex<T> getV() { return v; }
    public int getWeight() { return weight; }
    
    @Override
    public int compareTo(Edge<? super T> e) {
        return weight - e.getWeight();
    }
}
````

#### Graph Structure
````java
public class Graph<T> {
    private Set<Vertex<T>> vertices;
    private Set<Edge<T>> edges;
    private Map<Vertex<T>, List<VertexDistance<T>>> adjList;
    
    public Graph(Set<Vertex<T>> vertices, Set<Edge<T>> edges) {
        if (vertices == null || edges == null) {
            throw new IllegalArgumentException("Arguments cannot be null.");
        }
        
        this.vertices = new HashSet<>(vertices);
        this.edges = new HashSet<>(edges);
        this.adjList = new HashMap<>();
        
        // Initialize adjacency list
        for (Vertex<T> v : vertices) {
            adjList.put(v, new ArrayList<>());
        }
        
        // Populate adjacency list
        for (Edge<T> e : edges) {
            if (adjList.containsKey(e.getU())) {
                adjList.get(e.getU()).add(
                    new VertexDistance<>(e.getV(), e.getWeight())
                );
            } else {
                throw new IllegalArgumentException(
                    "Vertex set must contain all vertices of the graph.");
            }
        }
    }
}
````

#### Vertex Distance Helper
````java
public final class VertexDistance<T> 
    implements Comparable<VertexDistance<? super T>> {
    
    private final Vertex<T> vertex;
    private final int distance;
    
    public VertexDistance(Vertex<T> vertex, int distance) {
        this.vertex = vertex;
        this.distance = distance;
    }
    
    @Override
    public int compareTo(VertexDistance<? super T> pair) {
        return this.distance - pair.getDistance();
    }
}
````

### Performance Characteristics
| Operation | Average Case | Worst Case | Notes |
|-----------|--------------|------------|--------|
| Add Vertex | O(1) | O(1) | HashSet insertion |
| Add Edge | O(1) | O(1) | HashSet & ArrayList insertion |
| Find Vertex | O(1) | O(1) | HashSet lookup |
| Find Edge | O(1) | O(1) | HashSet lookup |
| Get Neighbors | O(1) | O(1) | HashMap & ArrayList access |
| Space | O(V + E) | O(V + E) | V vertices + E edges |


### Best Practices
#### 1. Creating Undirected Edges
````java
// Add both directions for undirected edges
vertices.add(vertexA);
vertices.add(vertexB);
edges.add(new Edge<>(vertexA, vertexB, weight));
edges.add(new Edge<>(vertexB, vertexA, weight));
````

#### 2. Vertex Creation
````java
// Ensure data validity
public static <T> Vertex<T> createVertex(T data) {
    if (data == null) {
        throw new IllegalArgumentException("Vertex data cannot be null");
    }
    return new Vertex<>(data);
}
````

#### 4. Edge Validation
````java
private boolean isValidEdge(Edge<T> edge) {
    return vertices.contains(edge.getU()) 
        && vertices.contains(edge.getV());
}
````

### ⚠️ Common Pitfalls
#### 1. Missing Graph Initialization
````java
// WRONG: Uninitialized collections
public Graph() {
    // Missing initialization
}

// CORRECT: Properly initialized collections
public Graph(Set<Vertex<T>> vertices, Set<Edge<T>> edges) {
    this.vertices = new HashSet<>(vertices);
    this.edges = new HashSet<>(edges);
    this.adjList = new HashMap<>();
    // ... rest of initialization
}
````

#### 2. Improper Edge Direction Handling
````java
// WRONG: Assuming bidirectional
adjList.get(edge.getV()).add(
    new VertexDistance<>(edge.getU(), edge.getWeight()));

// CORRECT: Respecting edge direction
adjList.get(edge.getU()).add(
    new VertexDistance<>(edge.getV(), edge.getWeight()));
````

This implementation provides a robust foundation for directed graph operations while maintaining type safety and efficient operations through appropriate data structure choices.

### References
[Introduction to Graphs](https://youtu.be/gXgEDyodOJU?si=ED9c2gKgXgDcDJvW)

# 🌳 Disjoint-Sets: Union-Find
![Disjoint-Sets](https://i.postimg.cc/y6yb5BFM/temp-Imagef5e-V06.avif)

A Disjoint Set (Union-Find) is a data structure that keeps track of elements partitioned into non-overlapping sets. It provides near-constant time operations to check if two elements are in the same set and to unite two sets, making it essential for algorithms like Kruskal's MST.

### Core Characteristics
-   🌳  **Tree-Based Structure**
    -   Each set is represented as a tree
    -   Elements point to their parent elements
    -   Root element represents the set identifier
    -   Path compression for efficiency
-   🔍  **Find Operation**
    -   Identifies the set an element belongs to
    -   Implements path compression
    -   Returns the root element
    -   Amortized O(1) time complexity
-   🤝  **Union Operation**
    -   Merges two different sets
    -   Uses union by rank
    -   Maintains tree balance
    -   Prevents deep hierarchies

### Implementation Details
#### Structure
````java
private static class DisjointSetNode<T> {
    private DisjointSetNode<T> parent;
    private T data;
    private int rank;
    
    public DisjointSetNode(T data) {
        this.parent = this;  // Node initially points to itself
        this.data = data;
        this.rank = 0;
    }
}
````

#### Base Structure
````java
public class DisjointSet<T> {
    private Map<T, DisjointSetNode<T>> disjointSet;
    
    public DisjointSet() {
        disjointSet = new HashMap<>();
    }
}
````

### Core Operations
#### Find Operation
````java
public T find(T data) {
    if (!disjointSet.containsKey(data)) {
        disjointSet.put(data, new DisjointSetNode<>(data));
    }
    return find(disjointSet.get(data)).getData();
}

private DisjointSetNode<T> find(DisjointSetNode<T> curr) {
    DisjointSetNode<T> parent = curr.getParent();
    
    if (parent == curr) {
        return curr;  // Found root
    }
    
    // Path compression: Make all nodes point to root
    parent = find(curr.getParent());
    curr.setParent(parent);
    return parent;
}
````

### 📊 Performance Characteristics
| Operation | Amortized Time | Worst Case | Notes |
|-----------|---------------|------------|--------|
| Make Set | O(1) | O(1) | Creates new set |
| Find | O(α(n)) | O(log n) | With path compression |
| Union | O(α(n)) | O(log n) | With union by rank |
| Space | O(n) | O(n) | n elements |

Note: α(n) is the inverse Ackermann function, which grows extremely slowly and is effectively constant for all practical values of n. 

### 💡 Best Practices
#### 1. Path Compression
````java
// Always update parent pointers during find
private DisjointSetNode<T> find(DisjointSetNode<T> node) {
    if (node != node.getParent()) {
        node.setParent(find(node.getParent())); // Compress path
    }
    return node.getParent();
}
````

#### 2. Union by Rank
````java
// Always consider ranks when unioning
if (firstParent.getRank() < secondParent.getRank()) {
    firstParent.setParent(secondParent);
} else {
    secondParent.setParent(firstParent);
    if (firstParent.getRank() == secondParent.getRank()) {
        firstParent.setRank(firstParent.getRank() + 1);
    }
}
````

#### 3. Lazy Initialization
````java
public T find(T data) {
    if (!disjointSet.containsKey(data)) {
        disjointSet.put(data, new DisjointSetNode<>(data));
    }
    // Continue with find operation
}
````

### ⚠️ Common Pitfalls
#### 1. Missing Path Compression
````java
// WRONG: No path compression
private DisjointSetNode<T> find(DisjointSetNode<T> node) {
    while (node != node.getParent()) {
        node = node.getParent();
    }
    return node;
}

// CORRECT: With path compression
private DisjointSetNode<T> find(DisjointSetNode<T> node) {
    if (node != node.getParent()) {
        node.setParent(find(node.getParent()));
    }
    return node.getParent();
}
````

#### 2. Incorrect Union Operation
````java
// WRONG: No path compression
private DisjointSetNode<T> find(DisjointSetNode<T> node) {
    while (node != node.getParent()) {
        node = node.getParent();
    }
    return node;
}

// CORRECT: With path compression
private DisjointSetNode<T> find(DisjointSetNode<T> node) {
    if (node != node.getParent()) {
        node.setParent(find(node.getParent()));
    }
    return node.getParent();
}
````

This implementation provides an efficient foundation for set operations used in graph algorithms, particularly Kruskal's Minimum Spanning Tree algorithm, with optimizations for both time and space complexity.

### References
[Union Find Data Structure](https://youtu.be/ayW5B2W9hfo?si=-6kosBXm4AK0u9pC)

# 📚 Other Advanced Structures

###  🔎 Trie
[Trie](https://youtube.com/playlist?list=PLEJXowNB4kPyi859E6qGUs7jlpQehJndl&si=9xfexgOQ7DaSU_h_)

### 🔎 Skip Lists
[Skip List Introduction](https://youtu.be/hqHwQUdTgLM?si=oaf0LW2DRyVO4lP5)
[Skip Lists Insertion and Deletion](https://youtu.be/1G8h3u6Thzs?si=ykbCCfLzIFW4oSa_)


