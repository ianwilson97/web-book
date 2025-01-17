
# 📘 Introduction to Algorithms

Algorithms are systematic procedures for solving computational problems and manipulating data. Understanding algorithms is crucial for developing efficient software solutions and optimizing program performance. This guide explores essential algorithms, their implementations, and practical applications in software engineering.

### 🎯 Why Algorithms Matter
-   🚀  **Performance Optimization**: Choose the right algorithm to dramatically improve execution speed
-   💻  **System Scalability**: Build solutions that efficiently handle growing data volumes
-   💼  **Technical Interviews**: Essential knowledge for coding interviews at top tech companies
-   🔄  **Problem-Solving**: Master fundamental approaches to computational challenges
-   🌟  **Competitive Programming**: Critical for algorithmic contests and competitions

### 📚 Guide Structure
Each algorithm section covers:

-   Step-by-step explanation
-   Implementation details
-   Time and space complexity analysis
-   Common optimization techniques
-   Best practices and use cases
-   Code examples and gotchas

### 🗂️ Categories of Algorithms
### 📊 Sorting Algorithms
Transform unordered collections into ordered sequences:

-   **Bubble Sort**:
    -   Simple comparison-based sorting
    -   Best for: Educational purposes, tiny datasets
-   **Selection Sort**:
    -   In-place comparison sorting
    -   Best for: Small arrays, minimal memory
-   **Insertion Sort**:
    -   Adaptive, stable sorting
    -   Best for: Nearly sorted data, online sorting
-   **Heap Sort**:
    -   Comparison-based sorting using heap
    -   Best for: Large datasets, guaranteed performance
-   **Quick Sort**:
    -   Divide-and-conquer approach
    -   Best for: General-purpose sorting, large datasets
-   **Merge Sort**:
    -   Stable, divide-and-conquer sorting
    -   Best for: Linked lists, external sorting

### 🔍 Searching Algorithms
Efficiently locate elements in datasets:

-   **Linear Search**:
    -   Sequential element checking
    -   Best for: Small or unsorted datasets
-   **Binary Search**:
    -   Divide-and-conquer searching
    -   Best for: Sorted arrays, large datasets

### 🕸️ Graph Algorithms
Navigate and analyze network structures:

-   **Breadth First Search (BFS)**:
    -   Level-by-level traversal
    -   Best for: Shortest paths, web crawling
-   **Depth First Search (DFS)**:
    -   Deep traversal exploration
    -   Best for: Maze solving, topological sorting
-   **Bellman Ford's Algorithm**:
    -   Single-source shortest paths
    -   Best for: Graphs with negative edges
-   **Dijkstra's Algorithm**:
    -   Efficient shortest path finding
    -   Best for: GPS, network routing
-   __A_  Algorithm_*:
    -   Heuristic pathfinding
    -   Best for: Game AI, navigation systems

### 🎯 Greedy Algorithms
Make locally optimal choices:

-   **Huffman Coding**:
    -   Data compression
    -   Best for: File compression, encoding
-   **Kruskal's Algorithm**:
    -   Minimum spanning tree
    -   Best for: Network design
-   **Ford-Fulkerson Algorithm**:
    -   Maximum flow problems
    -   Best for: Network flow optimization
-   **Prim's Algorithm**:
    -   Minimum spanning tree
    -   Best for: Dense graphs

### 🔤 Substring Search Algorithms
Pattern matching in text:

-   **Brute Force Search**:
    -   Simple pattern matching
    -   Best for: Short patterns
-   **Rabin-Karp**:
    -   Hash-based pattern matching
    -   Best for: Multiple pattern search
-   **Knuth-Morris-Pratt**:
    -   Efficient single pattern matching
    -   Best for: Single pattern in large text
-   **Boyer-Moore**:
    -   Fast pattern matching
    -   Best for: Long patterns

### ⏱️ Time Complexity Overview

| Algorithm | Best Case | Average Case | Worst Case | Space |
|-----------|-----------|--------------|------------|-------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | O(1) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Linear Search | O(1) | O(n) | O(n) | O(1) |
| Binary Search | O(1) | O(log n) | O(log n) | O(1) |
| BFS | O(V + E) | O(V + E) | O(V + E) | O(V) |
| DFS | O(V + E) | O(V + E) | O(V + E) | O(V) |
| Bellman Ford | O(VE) | O(VE) | O(VE) | O(V) |
| Dijkstra | O(E log V) | O(E log V) | O(E log V) | O(V) |
| A* | O(E) | O(E) | O(V²) | O(V) |
| Huffman Coding | O(n log n) | O(n log n) | O(n log n) | O(n) |
| Kruskal's Algorithm | O(E log E) | O(E log E) | O(E log E) | O(V) |
| Ford-Fulkerson | O(EF)* | O(EF)* | O(EF)* | O(V + E) |
| Prim's Algorithm | O(E log V) | O(E log V) | O(E log V) | O(V) |
| Brute Force Search | O(n) | O(mn) | O(mn) | O(1) |
| Rabin-Karp | O(m + n) | O(m + n) | O(mn) | O(1) |
| Knuth-Morris-Pratt | O(m + n) | O(m + n) | O(m + n) | O(m) |
| Boyer-Moore | O(n/m) | O(n) | O(mn) | O(m) |

### References
[Data Structures and Algorithms Notes](https://drive.google.com/file/d/1LaF74WE-jMvdlZ0FLwSWRxKVjO75iv8z/view?usp=sharing)


## 🔄 Sorting Algorithms
### Introduction
Sorting algorithms are fundamental procedures that arrange elements in a specific order, typically in ascending or descending sequence. Understanding these algorithms is crucial for efficient data manipulation and problem-solving in software development.

### 📘 Overview

Sorting algorithms are fundamental procedures that organize data in a specific order. Understanding these algorithms is crucial for:

-   🎯  **Efficient Data Organization**: Transform unordered data into ordered sequences
-   💻  **Performance Optimization**: Choose the right algorithm for your data size and type
-   🔍  **Interview Preparation**: Common technical interview topic
-   🧮  **Algorithm Foundation**: Building block for more complex algorithms
-   📊  **Data Analysis**: Essential for data processing and analysis


### 📝 Common Characteristics

### 🎯 Algorithm Properties

-   **Stability**: Whether relative order of equal elements is preserved
-   **In-Place**: Whether additional space is required
-   **Adaptivity**: Whether performance improves with partially sorted data

### ⚡ Performance Metrics

-   **Time Complexity**: How runtime scales with input size
-   **Space Complexity**: How memory usage scales with input size
-   **Best/Worst Cases**: Performance bounds under different conditions


## 🔍 Basic Sorting Algorithms
### 🔎 Implementation Details

### 1️⃣ Bubble Sort

A simple comparison-based algorithm that repeatedly steps through the list.

### 📊 Properties

-   ✅ In-place sorting
-   ✅ Stable algorithm
-   ✅ Adaptive behavior
-   🔄 Time: O(n²) worst/average, O(n) best
-   💾 Space: O(1)

### 💡 Best Used For:

-   Educational purposes
-   Tiny datasets
-   When simplicity is preferred over efficiency
-   Teaching sorting concepts
````java
public static <T> void bubbleSort(T[] arr, Comparator<T> comparator) {
    if (arr == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    for (int i = 0; i < arr.length - 1; i++) {
        boolean swapped = false;
        for (int j = 0; j < arr.length - i - 1; j++) {
            if (comparator.compare(arr[j], arr[j + 1]) > 0) {
                // Swap elements
                T temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swapped = true;
            }
        }
        // If no swapping occurred, array is sorted
        if (!swapped) break;
    }
}
````

### 🔑 Key Tips:

-   Use swapped flag to optimize for already sorted arrays
-   Each pass bubbles up the largest element
-   Consider cocktail sort variation for better performance
-   Good for visualizing sorting algorithms

### Reference
[Bubble Sort](https://youtu.be/Jdtq5uKz-w4?si=q0_frwVK6Lp4NNtM)

### 2️⃣ Selection Sort

An in-place comparison sorting algorithm that divides the input into a sorted and unsorted region.

### 📊 Properties

-   ✅ In-place sorting
-   ❌ Not stable
-   ❌ Not adaptive
-   🔄 Time: O(n²) all cases
-   💾 Space: O(1)

### 💡 Best Used For:

-   Small arrays
-   When memory is limited
-   When number of swaps needs to be minimized
-   Systems where write operations are costly

````java
public static <T> void selectionSort(T[] arr, Comparator<T> comparator) {
    if (arr == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    for (int i = 0; i < arr.length - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < arr.length; j++) {
            if (comparator.compare(arr[j], arr[minIndex]) < 0) {
                minIndex = j;
            }
        }
        // Swap with minimum element
        T temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }
}
````
### 🔑 Key Tips:

-   Makes minimum number of swaps (O(n))
-   Good when memory writes are expensive
-   Always performs O(n²) comparisons
-   Can be modified to be stable with additional space

### References
[Selection Sort](https://youtu.be/GUDLRan2DWM?si=tJoeaVl2doS9oR7Q)

### 3️⃣ Insertion Sort

A simple and adaptive sorting algorithm that builds the final sorted array one element at a time.

### 📊 Properties

-   ✅ In-place sorting
-   ✅ Stable algorithm
-   ✅ Adaptive behavior
-   🔄 Time: O(n²) worst/average, O(n) best
-   💾 Space: O(1)

### 💡 Best Used For:

-   Small datasets (< 50 elements)
-   Nearly sorted arrays
-   Online sorting (real-time data)
-   When simplicity is required

````java
public static <T> void insertionSort(T[] arr, Comparator<T> comparator) {
    if (arr == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    for (int i = 1; i < arr.length; i++) {
        T key = arr[i];
        int j = i - 1;
        while (j >= 0 && comparator.compare(arr[j], key) > 0) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
````

### 🔑 Key Tips:

-   Excellent for small datasets
-   Very efficient for nearly sorted arrays
-   Works well with continuous insertions
-   Often used in hybrid sorting algorithms

### 📚 Common Implementation Pitfalls

-   ⚠️ Forgetting null checks for array and comparator
-   ⚠️ Incorrect boundary conditions in loops
-   ⚠️ Unnecessary swaps that can be avoided
-   ⚠️ Not considering stability requirements

### References
[Insertion Sort](https://youtu.be/i-SKeOcBwko?si=svEhnHfJc4wyISjv)

### 💡 Quick Tips for Basic Sorting

-   🎯 Choose Insertion Sort for tiny arrays or nearly sorted data
-   🔄 Use Selection Sort when memory writes are expensive
-   📊 Bubble Sort is mainly for educational purposes
-   🧪 Test with different input sizes and patterns
-   📝 Consider stability requirements when choosing an algorithm

## 🔄 Advanced Sorting Algorithms
### 🚀 Overview

These algorithms represent more sophisticated sorting approaches, offering better performance for larger datasets:

-   📈  **Scalable Performance**: Efficient for large datasets
-   🔄  **Divide & Conquer**: Break complex problems into smaller ones
-   💫  **Advanced Techniques**: Utilize sophisticated sorting strategies
-   🎯  **Production Ready**: Commonly used in real-world applications

### 🔍 Implementation Details

### 1️⃣ Heap Sort

A comparison-based sorting algorithm using a binary heap data structure.

### 📊 Properties

-   ✅ In-place sorting
-   ❌ Not stable
-   ❌ Not adaptive
-   🔄 Time: O(n log n) all cases
-   💾 Space: O(1)

### 💡 Best Used For:

-   Large datasets
-   Memory-constrained systems
-   When stable sorting isn't required
-   Systems requiring guaranteed O(n log n)

````java
public static int[] heapSort(List<Integer> data) {
    if (data == null) {
        throw new IllegalArgumentException("List cannot be null");
    }

    // Using Java's PriorityQueue for heap implementation
    PriorityQueue<Integer> heap = new PriorityQueue<>(data);
    int[] sorted = new int[data.size()];
    
    // Extract elements from heap in sorted order
    for (int i = 0; !heap.isEmpty(); i++) {
        sorted[i] = heap.remove();
    }
    
    return sorted;
}
````

### 🔑 Key Tips:

-   Use built-in PriorityQueue for simple implementation
-   Helpful for implementing priority scheduling
-   Excellent for top-K problems
-   In-place sorting saves memory

### References
[Heap Sort](https://youtu.be/2DmK_H7IdTo?si=zBP8gooaej_fUyis)

### 2️⃣ Quick Sort

A highly efficient, comparison-based algorithm using divide-and-conquer strategy.

### 📊 Properties

-   ✅ In-place sorting
-   ❌ Not stable
-   ❌ Not adaptive
-   🔄 Time: O(n²) worst, O(n log n) average/best
-   💾 Space: O(log n)

### 💡 Best Used For:

-   Large datasets
-   Systems with good cache locality
-   General-purpose sorting
-   When average case performance is important
````java
public static <T> void quickSort(T[] arr, Comparator<T> comparator, Random rand) {
    if (arr == null || comparator == null || rand == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }
    quickSortHelper(arr, comparator, rand, 0, arr.length - 1);
}

private static <T> void quickSortHelper(T[] arr, Comparator<T> comp, 
    Random rand, int start, int end) {
    if (start < end) {
        // Choose random pivot
        int pivotIdx = rand.nextInt(end - start + 1) + start;
        T pivot = arr[pivotIdx];
        
        // Move pivot to start
        swap(arr, start, pivotIdx);
        
        // Partition
        int i = start + 1;
        int j = end;
        while (i <= j) {
            while (i <= j && comp.compare(arr[i], pivot) <= 0) i++;
            while (i <= j && comp.compare(arr[j], pivot) > 0) j--;
            if (i < j) swap(arr, i, j);
        }
        
        // Place pivot in correct position
        swap(arr, start, j);
        
        // Recursive calls
        quickSortHelper(arr, comp, rand, start, j - 1);
        quickSortHelper(arr, comp, rand, j + 1, end);
    }
}
````

### 🔑 Key Tips:

-   Use random pivot selection to avoid worst case
-   Consider median-of-three for pivot selection
-   Switch to insertion sort for small subarrays
-   Be cautious with already sorted arrays

### References
[Quick Sort](https://youtu.be/COk73cpQbFQ?si=CBZe5ErZfr4Ugq2M)

### 3️⃣ Merge Sort

A stable, divide-and-conquer algorithm with guaranteed performance.

### 📊 Properties

-   ❌ Not in-place
-   ✅ Stable algorithm
-   ❌ Not adaptive
-   🔄 Time: O(n log n) all cases
-   💾 Space: O(n)

### 💡 Best Used For:

-   Large datasets
-   When stability is required
-   External sorting
-   Linked list sorting

````java
public static <T> void mergeSort(T[] arr, Comparator<T> comparator) {
    if (arr == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    if (arr.length > 1) {
        T[] firstHalf = (T[]) new Object[arr.length / 2];
        T[] secondHalf = (T[]) new Object[arr.length - arr.length / 2];
        
        // Split array into halves
        System.arraycopy(arr, 0, firstHalf, 0, firstHalf.length);
        System.arraycopy(arr, firstHalf.length, secondHalf, 0, secondHalf.length);
        
        // Recursive sorting
        mergeSort(firstHalf, comparator);
        mergeSort(secondHalf, comparator);
        merge(firstHalf, secondHalf, arr, comparator);
    }
}

private static <T> void merge(T[] firstHalf, T[] secondHalf, T[] arr, 
                            Comparator<T> comparator) {
    int i = 0;  // Index for firstHalf array
    int j = 0;  // Index for secondHalf array
    int k = 0;  // Index for merged array

    // Compare and merge elements from both halves
    while (i < firstHalf.length && j < secondHalf.length) {
        if (comparator.compare(firstHalf[i], secondHalf[j]) <= 0) {
            arr[k++] = firstHalf[i++];
        } else {
            arr[k++] = secondHalf[j++];
        }
    }

    // Copy remaining elements from firstHalf (if any)
    while (i < firstHalf.length) {
        arr[k++] = firstHalf[i++];
    }

    // Copy remaining elements from secondHalf (if any)
    while (j < secondHalf.length) {
        arr[k++] = secondHalf[j++];
    }
}
````
### 🔑 Key Tips:

-   Perfect for external sorting
-   Great for parallel processing
-   Stable sorting guaranteed
-   Consider in-place merge for space optimization
### 🔑 Additional Merge Tips:

-   The  `<=`  in the comparison ensures stability
-   Using separate arrays avoids complex in-place merging
-   Sequential access pattern is cache-friendly
-   Can be optimized for nearly sorted arrays

### References
[Merge Sort](https://youtu.be/TzeBrDU-JaY?si=o-hPGeX8YGxKGM7W)

### 🎯 Advanced Implementation Strategies

### 💡 Optimization Tips

-   🔄 Use hybrid approaches for better performance
-   📊 Consider input size for algorithm selection
-   💾 Balance memory usage vs. speed
-   ⚡ Optimize for cache efficiency

### ⚠️ Common Pitfalls

-   Memory management in recursive implementations
-   Pivot selection in QuickSort
-   Improper handling of equal elements
-   Not considering stability requirements
### ⚠️ Merge Function Pitfalls:

-   Not handling empty arrays properly
-   Incorrect index management
-   Forgetting to copy remaining elements
-   Improper comparison for stability

# 🔍 Searching Algorithms

## 📘 Introduction

Searching algorithms are fundamental techniques for finding specific elements within data structures. Understanding these algorithms is crucial for:

-   🎯  **Data Retrieval**: Efficiently locate specific elements
-   💻  **Algorithm Design**: Foundation for more complex algorithms
-   🔍  **Interview Preparation**: Common technical interview topic
-   🧮  **Problem Solving**: Essential for many programming tasks
-   📊  **Performance Optimization**: Choose right approach for your data

### 🔍 Basic Search Algorithms

### 1️⃣ Linear Search

A simple sequential search algorithm that checks each element until a match is found.

### 📊 Properties

-   ✅ Works on unsorted data
-   ✅ Simple implementation
-   ✅ Minimal space requirement
-   🔄 Time: O(n) worst/average, O(1) best
-   💾 Space: O(1)

### 💡 Best Used For:

-   Small datasets
-   Unsorted collections
-   One-time searches
-   When simplicity is preferred
-   Finding all occurrences
````java
public static <T> int linearSearch(T[] arr, T target, Comparator<T> comparator) {
    if (arr == null || target == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    for (int i = 0; i < arr.length; i++) {
        if (comparator.compare(arr[i], target) == 0) {
            return i;  // Element found, return index
        }
    }
    return -1;  // Element not found
}
````
### 🔑 Key Tips:

-   Consider early termination if possible
-   Use for unsorted or small datasets
-   Good for finding multiple occurrences
-   Consider parallel search for large datasets

### 2️⃣ Binary Search

An efficient algorithm that requires sorted data and uses divide-and-conquer strategy.

### 📊 Properties

-   ✅ Very efficient for large datasets
-   ❌ Requires sorted data
-   ✅ Logarithmic time complexity
-   🔄 Time: O(log n) worst/average, O(1) best
-   💾 Space: O(1) iterative, O(log n) recursive

### 💡 Best Used For:

-   Large sorted datasets
-   Frequent searches
-   When data is already sorted
-   Finding insertion points
-   Range queries
````java
// Iterative Implementation
public static <T> int binarySearch(T[] arr, T target, Comparator<T> comparator) {
    if (arr == null || target == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }

    int left = 0;
    int right = arr.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;
        int comparison = comparator.compare(arr[mid], target);

        if (comparison == 0) {
            return mid;  // Element found
        } else if (comparison < 0) {
            left = mid + 1;  // Search right half
        } else {
            right = mid - 1;  // Search left half
        }
    }
    return -1;  // Element not found
}

// Recursive Implementation
public static <T> int binarySearchRecursive(T[] arr, T target, 
                                          Comparator<T> comparator) {
    if (arr == null || target == null || comparator == null) {
        throw new IllegalArgumentException("Inputs cannot be null");
    }
    return binarySearchHelper(arr, target, comparator, 0, arr.length - 1);
}

private static <T> int binarySearchHelper(T[] arr, T target, 
                                        Comparator<T> comparator, 
                                        int left, int right) {
    if (left > right) {
        return -1;
    }

    int mid = left + (right - left) / 2;
    int comparison = comparator.compare(arr[mid], target);

    if (comparison == 0) {
        return mid;
    } else if (comparison < 0) {
        return binarySearchHelper(arr, target, comparator, mid + 1, right);
    } else {
        return binarySearchHelper(arr, target, comparator, left, mid - 1);
    }
}
````

### 🔑 Key Tips:

-   Use  `left + (right - left) / 2`  to avoid integer overflow
-   Consider iterative vs recursive based on needs
-   Useful for finding insertion points
-   Can be modified for fuzzy searching

### References
[Binary Search](https://youtu.be/j5uXyPJ0Pew?si=-49mGr1l7lVuQWdF)

## 📊 Algorithm Comparison

| Feature | Linear Search | Binary Search |
|---------|---------------|---------------|
| Time Complexity (Worst) | O(n) | O(log n) |
| Time Complexity (Best) | O(1) | O(1) |
| Space Complexity | O(1) | O(1) iterative, O(log n) recursive |
| Sorted Data Required | No | Yes |
| Multiple Occurrences | Easy to find all | Finds one occurrence |
| Implementation Complexity | Simple | Moderate |
| Cache Performance | Good for small data | May have cache misses |

### 💡 Implementation Best Practices

### 🎯 General Tips

-   Always validate input parameters
-   Handle edge cases (empty arrays, null values)
-   Consider return type (index vs boolean vs element)
-   Use appropriate comparator functions

### ⚠️ Common Pitfalls

-   Off-by-one errors in binary search
-   Not checking for null values
-   Assuming data is sorted for binary search
-   Integer overflow in mid-point calculation

### 🔍 Advanced Considerations

-   Duplicate elements handling
-   Custom comparison logic
-   Parallel search for large datasets
-   Cache-friendly implementations

### 🎯 When to Use Each

-   📌  **Linear Search**:
    -   Small datasets
    -   Unsorted data
    -   Finding all occurrences
    -   Simple implementation needed
-   📌  **Binary Search**:
    -   Large sorted datasets
    -   Frequent searches
    -   Finding insertion points
    -   Performance critical operations

# 🕸️ Graph Algorithms

## 📘 Introduction

Graph algorithms are essential techniques for solving problems that involve network-like structures. Understanding these algorithms is crucial for:

-   🗺️  **Network Analysis**: Navigate and analyze complex networks
-   🔍  **Path Finding**: Find optimal routes between nodes
-   🌐  **Web Crawling**: Systematically browse and analyze web pages
-   🎮  **Game Development**: Power AI and navigation systems
-   📱  **Social Networks**: Analyze relationships and connections

## 🔑 Key Graph Concepts

-   **Vertex (Node)**: Points in the graph
-   **Edge**: Connections between vertices
-   **Path**: Sequence of vertices connected by edges
-   **Cycle**: Path that starts and ends at same vertex
-   **Connected Component**: Group of connected vertices

## 🔍 Basic Graph Traversal

### 1️⃣ Breadth First Search (BFS)

A traversal algorithm that explores a graph level by level.

### 📊 Properties

-   ✅ Finds shortest path in unweighted graphs
-   ✅ Explores nodes level by level
-   ✅ Uses queue data structure
-   🔄 Time: O(V + E)
-   💾 Space: O(V)

### 💡 Best Used For:

-   Finding shortest paths
-   Level-order traversal
-   Web crawling
-   Network broadcasting
-   Finding connected components
````java
public class Graph {
    private Map<Vertex, List<Vertex>> adjList;
    
    public void bfs(Vertex start) {
        if (start == null) {
            throw new IllegalArgumentException("Start vertex cannot be null");
        }

        Queue<Vertex> queue = new LinkedList<>();
        Set<Vertex> visited = new HashSet<>();
        
        // Start the traversal
        queue.offer(start);
        visited.add(start);
        
        while (!queue.isEmpty()) {
            Vertex current = queue.poll();
            System.out.println("Visiting: " + current.getValue());
            
            // Process all neighbors
            for (Vertex neighbor : adjList.get(current)) {
                if (!visited.contains(neighbor)) {
                    visited.add(neighbor);
                    queue.offer(neighbor);
                }
            }
        }
    }
    
    // Version that tracks paths
    public Map<Vertex, Vertex> bfsWithPaths(Vertex start) {
        Queue<Vertex> queue = new LinkedList<>();
        Map<Vertex, Vertex> parentMap = new HashMap<>();
        
        queue.offer(start);
        parentMap.put(start, null);
        
        while (!queue.isEmpty()) {
            Vertex current = queue.poll();
            
            for (Vertex neighbor : adjList.get(current)) {
                if (!parentMap.containsKey(neighbor)) {
                    parentMap.put(neighbor, current);
                    queue.offer(neighbor);
                }
            }
        }
        
        return parentMap;
    }
}
````

### 🔑 Key Tips:

-   Use for shortest path in unweighted graphs
-   Great for level-by-level exploration
-   Consider space requirements for large graphs
-   Can be modified to find shortest path

### References
[Breadth First Search](https://youtu.be/oDqjPvD54Ss?si=Grejcv1Q6z6BgCzu)

### 2️⃣ Depth First Search (DFS)

A traversal algorithm that explores a graph by going as deep as possible before backtracking.

### 📊 Properties

-   ✅ Memory efficient for deep graphs
-   ✅ Natural recursive implementation
-   ✅ Can detect cycles
-   🔄 Time: O(V + E)
-   💾 Space: O(V) worst case

### 💡 Best Used For:

-   Topological sorting
-   Cycle detection
-   Maze solving
-   Path finding
-   Connected components

````java
public class Graph {
    private Map<Vertex, List<Vertex>> adjList;
    
    // Recursive DFS
    public void dfs(Vertex start) {
        if (start == null) {
            throw new IllegalArgumentException("Start vertex cannot be null");
        }

        Set<Vertex> visited = new HashSet<>();
        dfsHelper(start, visited);
    }
    
    private void dfsHelper(Vertex current, Set<Vertex> visited) {
        visited.add(current);
        System.out.println("Visiting: " + current.getValue());
        
        for (Vertex neighbor : adjList.get(current)) {
            if (!visited.contains(neighbor)) {
                dfsHelper(neighbor, visited);
            }
        }
    }
    
    // Iterative DFS using Stack
    public void dfsIterative(Vertex start) {
        if (start == null) {
            throw new IllegalArgumentException("Start vertex cannot be null");
        }

        Stack<Vertex> stack = new Stack<>();
        Set<Vertex> visited = new HashSet<>();
        
        stack.push(start);
        
        while (!stack.isEmpty()) {
            Vertex current = stack.pop();
            
            if (!visited.contains(current)) {
                visited.add(current);
                System.out.println("Visiting: " + current.getValue());
                
                // Add all unvisited neighbors to stack
                for (Vertex neighbor : adjList.get(current)) {
                    if (!visited.contains(neighbor)) {
                        stack.push(neighbor);
                    }
                }
            }
        }
    }
}
````

### 🔑 Key Tips:

-   Choose between recursive and iterative based on graph depth
-   Use for finding paths in mazes
-   Efficient for deep graph structures
-   Can be modified for cycle detection

### References
[Depth First Search](https://youtu.be/7fujbpJ0LB4?si=2BL0b9mKllr7XcCd)

## 📊 Algorithm Comparison

| Feature | BFS | DFS |
|---------|-----|-----|
| Time Complexity | O(V + E) | O(V + E) |
| Space Complexity | O(V) | O(V) |
| Implementation | Queue-based | Stack/Recursive |
| Path Finding | Shortest in unweighted | Any valid path |
| Memory Usage | More for wide graphs | More for deep graphs |
| Use Case | Level-wise traversal | Deep traversal |
| Completeness | Complete | Complete |

### 💡 Implementation Best Practices

### 🎯 General Tips

-   Always validate input parameters
-   Handle disconnected components
-   Consider space-time tradeoffs
-   Use appropriate data structures

### ⚠️ Common Pitfalls

-   Forgetting to mark nodes as visited
-   Infinite loops in cyclic graphs
-   Stack overflow in recursive DFS
-   Not handling disconnected components

### 🔍 Advanced Considerations

-   Graph representation choice
-   Memory management
-   Performance optimization
-   Edge case handling

# 🛣️ Shortest Path Algorithms
## 📘 Overview

Shortest path algorithms are essential for finding optimal routes between vertices in a graph. These algorithms are crucial for:

-   🗺️  **Navigation Systems**: Finding optimal routes
-   🌐  **Network Routing**: Optimizing network traffic
-   💰  **Financial Markets**: Currency exchange optimization
-   🎮  **Game Development**: Path-finding for AI
-   📡  **Network Design**: Infrastructure planning

## 🔍 Advanced Path-Finding Algorithms

### 1️⃣ Bellman-Ford Algorithm

An algorithm that finds shortest paths from a source vertex to all other vertices, even with negative edge weights.

### 📊 Properties

-   ✅ Handles negative edge weights
-   ✅ Detects negative cycles
-   ✅ Simple implementation
-   🔄 Time: O(VE)
-   💾 Space: O(V)

### 💡 Best Used For:

-   Graphs with negative weights
-   Detecting negative cycles
-   Currency exchange calculations
-   Network routing protocols
-   When edge weights can be negative
````java
public class Graph {
    private List<Edge> edges;
    private int V; // Number of vertices

    public class Edge {
        int source, destination, weight;
        
        Edge(int source, int destination, int weight) {
            this.source = source;
            this.destination = destination;
            this.weight = weight;
        }
    }

    public int[] bellmanFord(int source) {
        // Initialize distances
        int[] distances = new int[V];
        Arrays.fill(distances, Integer.MAX_VALUE);
        distances[source] = 0;

        // Relax all edges V-1 times
        for (int i = 0; i < V - 1; i++) {
            for (Edge edge : edges) {
                int u = edge.source;
                int v = edge.destination;
                int weight = edge.weight;

                if (distances[u] != Integer.MAX_VALUE && 
                    distances[u] + weight < distances[v]) {
                    distances[v] = distances[u] + weight;
                }
            }
        }

        // Check for negative weight cycles
        for (Edge edge : edges) {
            int u = edge.source;
            int v = edge.destination;
            int weight = edge.weight;

            if (distances[u] != Integer.MAX_VALUE && 
                distances[u] + weight < distances[v]) {
                throw new IllegalStateException("Graph contains negative weight cycle");
            }
        }

        return distances;
    }
}
````
### 🔑 Key Tips:

-   Use for detecting negative cycles
-   Good for small to medium graphs
-   Consider memory efficiency
-   Handle infinity values carefully

### References
[Shortest Path Algorithms (Bellman Ford & Dijkstra)](https://youtu.be/j0OUwduDOS0?si=nmbGXqfOW95lCaga)

### 2️⃣ Dijkstra's Algorithm

A greedy algorithm that finds the shortest path between nodes in a graph with non-negative edge weights.

### 📊 Properties

-   ✅ Efficient for non-negative weights
-   ✅ Finds optimal paths
-   ❌ Doesn't work with negative weights
-   🔄 Time: O(E log V) with binary heap
-   💾 Space: O(V)

### 💡 Best Used For:

-   Road navigation systems
-   Network routing
-   Social networks
-   Games pathfinding
-   Resource distribution
````java
public class Graph {
    private Map<Integer, List<Edge>> adjList;
    
    public class Edge {
        int destination;
        int weight;
        
        Edge(int destination, int weight) {
            this.destination = destination;
            this.weight = weight;
        }
    }

    public Map<Integer, Integer> dijkstra(int source) {
        // Priority queue for vertices with their distances
        PriorityQueue<Node> pq = new PriorityQueue<>(
            Comparator.comparingInt(node -> node.distance)
        );
        
        // Track distances and previous nodes
        Map<Integer, Integer> distances = new HashMap<>();
        Map<Integer, Integer> previous = new HashMap<>();
        
        // Initialize distances
        for (int vertex : adjList.keySet()) {
            distances.put(vertex, Integer.MAX_VALUE);
        }
        distances.put(source, 0);
        pq.offer(new Node(source, 0));

        while (!pq.isEmpty()) {
            Node current = pq.poll();
            int u = current.vertex;
            
            // Skip if we've found a better path
            if (current.distance > distances.get(u)) {
                continue;
            }

            // Check all neighboring vertices
            for (Edge edge : adjList.get(u)) {
                int v = edge.destination;
                int newDist = distances.get(u) + edge.weight;

                if (newDist < distances.get(v)) {
                    distances.put(v, newDist);
                    previous.put(v, u);
                    pq.offer(new Node(v, newDist));
                }
            }
        }

        return distances;
    }

    private class Node {
        int vertex;
        int distance;

        Node(int vertex, int distance) {
            this.vertex = vertex;
            this.distance = distance;
        }
    }
}
````
### 🔑 Key Tips:

-   Use priority queue for efficiency
-   Only works with non-negative weights
-   Consider path reconstruction
-   Can be optimized for specific use cases
## 📊 Algorithm Comparison

| Feature | Bellman-Ford | Dijkstra |
|---------|--------------|----------|
| Time Complexity | O(VE) | O(E log V) |
| Space Complexity | O(V) | O(V) |
| Handles Negative Weights | Yes | No |
| Detects Negative Cycles | Yes | N/A |
| Implementation | Simple | Moderate |
| Use Case | Negative weights | Positive weights |
| Performance | Slower | Faster |
| Memory Usage | Lower | Higher |
### 💡 Implementation Best Practices

### 🎯 General Tips

-   Validate input graphs and weights
-   Handle unreachable vertices
-   Consider path reconstruction
-   Implement proper error handling

### ⚠️ Common Pitfalls

-   Integer overflow in distance calculations
-   Not handling disconnected components
-   Improper handling of infinity values
-   Forgetting to check for negative cycles

### 🔍 Advanced Optimizations

-   Use Fibonacci heap for better theoretical performance
-   Bidirectional search for specific endpoints
-   A* modifications for heuristic improvements
-   Early termination for single-target searches

### References
[Shortest Path Algorithms (Bellman Ford & Dijkstras)](https://youtu.be/j0OUwduDOS0?si=nmbGXqfOW95lCaga)

# 💫 Greedy Algorithms
## 📘 Introduction

Greedy algorithms make locally optimal choices at each step, aiming for a global optimum. These algorithms are essential for:

-   🎯  **Optimization Problems**: Finding best solutions efficiently
-   💻  **Resource Management**: Allocating resources optimally
-   🌐  **Network Design**: Creating efficient network structures
-   📊  **Data Compression**: Reducing data size effectively
-   🔄  **Dynamic Solutions**: Solving problems step by step

## 🔍 Algorithm Deep Dive

### 1️⃣ Huffman Coding

A data compression technique that assigns variable-length codes to characters based on their frequencies.

### 📊 Properties

-   ✅ Optimal prefix codes
-   ✅ Lossless compression
-   ✅ Variable-length encoding
-   🔄 Time: O(n log n)
-   💾 Space: O(n)

### 💡 How It Works

1.  **Frequency Analysis**:
    -   Count frequency of each character
    -   Create leaf nodes for each character
2.  **Tree Construction**:
    -   Create min-heap of nodes
    -   Repeatedly merge two lowest frequency nodes
    -   New node's frequency = sum of children
3.  **Code Generation**:
    -   Traverse tree from root to leaves
    -   Left edge = 0, Right edge = 1
    -   Path to leaf = character's code

### 🎯 Example

For string: "HELLO WORLD"
````java
Character frequencies:
H: 1, E: 1, L: 3, O: 2, W: 1, R: 1, D: 1, (space): 1

Resulting codes might be:
L: 00
O: 01
H: 100
E: 101
W: 110
R: 1110
D: 1111
(space): 1000
````
### 🔑 Key Applications

-   Text file compression
-   Data transmission
-   Multimedia encoding
-   Network protocols
-   Storage optimization

### References
[Huffman Coding](https://youtu.be/B3y0RsVCyrw?si=djkN8j3NGkqGNCPp)

### 2️⃣ Kruskal's Algorithm

A minimum spanning tree algorithm that builds the tree by selecting edges in increasing order of weight.

### 📊 Properties

-   ✅ Finds global minimum
-   ✅ Works on disconnected graphs
-   ✅ Edge-focused approach
-   🔄 Time: O(E log E)
-   💾 Space: O(V)

### 💡 How It Works

1.  Sort all edges by weight
2.  Process edges in ascending order
3.  Add edge if it doesn't create cycle
4.  Use Union-Find data structure to detect cycles

````java
public class KruskalMST {
    private static class Edge implements Comparable<Edge> {
        int src, dest, weight;

        Edge(int src, int dest, int weight) {
            this.src = src;
            this.dest = dest;
            this.weight = weight;
        }

        @Override
        public int compareTo(Edge other) {
            return Integer.compare(this.weight, other.weight);
        }
    }

    private static class UnionFind {
        private final int[] parent;
        private final int[] rank;

        UnionFind(int size) {
            parent = new int[size];
            rank = new int[size];
            
            // Initialize each vertex as its own set
            for (int i = 0; i < size; i++) {
                parent[i] = i;
            }
        }

        // Find with path compression
        int find(int x) {
            if (parent[x] != x) {
                parent[x] = find(parent[x]);
            }
            return parent[x];
        }

        // Union by rank
        void union(int x, int y) {
            int rootX = find(x);
            int rootY = find(y);

            if (rootX != rootY) {
                if (rank[rootX] < rank[rootY]) {
                    parent[rootX] = rootY;
                } else if (rank[rootX] > rank[rootY]) {
                    parent[rootY] = rootX;
                } else {
                    parent[rootY] = rootX;
                    rank[rootX]++;
                }
            }
        }
    }

    public List<Edge> findMST(int V, List<Edge> edges) {
        List<Edge> mst = new ArrayList<>();
        UnionFind uf = new UnionFind(V);

        // Sort edges by weight
        edges.sort(Edge::compareTo);

        for (Edge edge : edges) {
            // If including this edge doesn't create a cycle
            if (uf.find(edge.src) != uf.find(edge.dest)) {
                mst.add(edge);
                uf.union(edge.src, edge.dest);
            }
        }

        return mst;
    }
}
````
### 🔑 Key Tips

-   **Edge Sorting**:
    -   Sort edges first for optimal selection
    -   Consider custom comparator for complex weights
-   **Union-Find Optimization**:
    -   Use path compression
    -   Implement union by rank
    -   Keep track of set sizes
-   **Implementation Considerations**:
    -   Handle disconnected components
    -   Validate input edges
    -   Consider edge cases (empty graph, single vertex)
-   **Performance Optimization**:
    -   Use efficient sorting algorithm
    -   Optimize Union-Find operations
    -   Consider early termination

### References
[Kruskal's Algorithm Introduction](https://youtu.be/JZBQLXgSGfs?si=e2XfI4BE5C00paqB)
[Kruskal's Algorithm in 2 mins](https://youtu.be/71UQH7Pr9kU?si=ji5cX99eGYXfmSdK)

## 📊 Algorithm Comparison

| Feature | Huffman Coding | Kruskal's Algorithm |
|---------|---------------|-------------------|
| Time Complexity | O(n log n) | O(E log E) |
| Space Complexity | O(n) | O(V) |
| Primary Use | Data Compression | Network Design |
| Data Structure | Priority Queue & Tree | Union-Find |
| Approach | Bottom-up | Global Greedy |
| Implementation | Moderate | Moderate |
| Output | Prefix Codes | Minimum Spanning Tree |

### 💡 Best Practices

### 🎯 General Tips

-   Validate input data
-   Handle edge cases
-   Use appropriate data structures
-   Consider performance optimizations

### ⚠️ Common Pitfalls

-   Not handling empty inputs
-   Incorrect cycle detection
-   Inefficient set operations
-   Poor edge weight handling
# 🌊 Advanced Greedy Algorithms

## 📘 Network Flow and Spanning Tree Algorithms

These algorithms solve complex network optimization problems, essential for:

-   🌐  **Network Flow**: Maximizing throughput in networks
-   🔄  **Resource Allocation**: Optimal distribution of resources
-   🌳  **Tree Construction**: Building optimal spanning trees
-   📊  **Network Design**: Creating efficient network topologies
-   🚰  **Flow Networks**: Modeling pipeline and traffic systems

## 🔍 Algorithm Details

### 1️⃣ Ford-Fulkerson Algorithm

A method for computing maximum flow in a flow network.

### 📊 Properties

-   ✅ Finds maximum flow
-   ✅ Uses augmenting paths
-   ✅ Iterative improvement
-   🔄 Time: O(EF) where F is max flow
-   💾 Space: O(V + E)

### 💡 Best Used For:

-   Network capacity planning
-   Traffic routing
-   Resource distribution
-   Bipartite matching
-   Pipeline optimization
````java
public class FordFulkerson {
    private static class Edge {
        int dest, capacity, flow;
        Edge reverse;  // Reference to reverse edge

        Edge(int dest, int capacity) {
            this.dest = dest;
            this.capacity = capacity;
            this.flow = 0;
        }

        int remainingCapacity() {
            return capacity - flow;
        }

        void addFlow(int amount) {
            flow += amount;
            reverse.flow -= amount;
        }
    }

    private final List<List<Edge>> graph;
    private final int V;

    public FordFulkerson(int vertices) {
        this.V = vertices;
        this.graph = new ArrayList<>(V);
        for (int i = 0; i < V; i++) {
            graph.add(new ArrayList<>());
        }
    }

    public void addEdge(int from, int to, int capacity) {
        // Create forward and reverse edges
        Edge forward = new Edge(to, capacity);
        Edge reverse = new Edge(from, 0);
        
        // Link the edges
        forward.reverse = reverse;
        reverse.reverse = forward;
        
        // Add edges to graph
        graph.get(from).add(forward);
        graph.get(to).add(reverse);
    }

    public int maxFlow(int source, int sink) {
        int maxFlow = 0;

        while (true) {
            // Find augmenting path using BFS
            int[] parent = new int[V];
            Edge[] parentEdge = new Edge[V];
            Arrays.fill(parent, -1);

            Queue<Integer> queue = new LinkedList<>();
            queue.offer(source);
            parent[source] = source;

            while (!queue.isEmpty() && parent[sink] == -1) {
                int current = queue.poll();

                for (Edge edge : graph.get(current)) {
                    if (parent[edge.dest] == -1 && edge.remainingCapacity() > 0) {
                        parent[edge.dest] = current;
                        parentEdge[edge.dest] = edge;
                        queue.offer(edge.dest);
                    }
                }
            }

            // If no augmenting path found, break
            if (parent[sink] == -1) break;

            // Find minimum residual capacity along the path
            int bottleneck = Integer.MAX_VALUE;
            for (int v = sink; v != source; v = parent[v]) {
                bottleneck = Math.min(bottleneck, parentEdge[v].remainingCapacity());
            }

            // Update flow along the path
            for (int v = sink; v != source; v = parent[v]) {
                parentEdge[v].addFlow(bottleneck);
            }

            maxFlow += bottleneck;
        }

        return maxFlow;
    }
}
````
### 🔑 Key Tips:

-   Implement residual graph carefully
-   Use BFS for finding augmenting paths
-   Track reverse edges
-   Handle bottleneck calculations properly

### References
[Ford-Fulkerson Algorithm](https://youtu.be/LdOnanfc5TM?si=CWSkBFibazbFskMp)
[Ford-Fulkerson Algorithm](https://youtu.be/Tl90tNtKvxs?si=NCyoulWAu_-4fPVe)

### 2️⃣ Prim's Algorithm

A greedy approach for finding minimum spanning tree, growing from a single vertex.

### 📊 Properties

-   ✅ Optimal solution
-   ✅ Local optimization
-   ✅ Vertex-based approach
-   🔄 Time: O(E log V)
-   💾 Space: O(V)

### 💡 Best Used For:

-   Network design
-   Cluster analysis
-   Circuit design
-   Cost minimization
-   Network optimization
````java
public class PrimMST {
    private static class Edge {
        int dest, weight;

        Edge(int dest, int weight) {
            this.dest = dest;
            this.weight = weight;
        }
    }

    private static class Vertex implements Comparable<Vertex> {
        int id, key;
        
        Vertex(int id, int key) {
            this.id = id;
            this.key = key;
        }

        @Override
        public int compareTo(Vertex other) {
            return Integer.compare(this.key, other.key);
        }
    }

    public List<Edge> findMST(List<List<Edge>> graph) {
        int V = graph.size();
        List<Edge> mst = new ArrayList<>();
        
        // Priority queue for selecting minimum weight edge
        PriorityQueue<Vertex> pq = new PriorityQueue<>();
        int[] key = new int[V];
        int[] parent = new int[V];
        boolean[] inMST = new boolean[V];

        // Initialize keys and parent
        Arrays.fill(key, Integer.MAX_VALUE);
        Arrays.fill(parent, -1);

        // Start with vertex 0
        key[0] = 0;
        pq.offer(new Vertex(0, 0));

        while (!pq.isEmpty()) {
            int u = pq.poll().id;
            
            // Skip if already processed
            if (inMST[u]) continue;
            
            inMST[u] = true;

            // Add edge to MST if not root
            if (parent[u] != -1) {
                mst.add(new Edge(u, key[u]));
            }

            // Update keys of adjacent vertices
            for (Edge edge : graph.get(u)) {
                int v = edge.dest;
                if (!inMST[v] && edge.weight < key[v]) {
                    key[v] = edge.weight;
                    parent[v] = u;
                    pq.offer(new Vertex(v, key[v]));
                }
            }
        }

        return mst;
    }
}
````
### 🔑 Key Tips:

-   Use priority queue for efficiency
-   Maintain key values properly
-   Handle disconnected components
-   Consider dense vs sparse graphs

### References
[Prim's Algorithm](https://youtu.be/YyLaRffCdk4?si=MlqRXZRcsY-OG7ZK)
[Prim's MST Algorithm](https://youtu.be/jsmMtJpPnhU?si=yJdtLBHxKf6yOw-k)

## 📊 Algorithm Comparison

| Feature | Ford-Fulkerson | Prim's Algorithm |
|---------|---------------|------------------|
| Time Complexity | O(EF) | O(E log V) |
| Space Complexity | O(V + E) | O(V) |
| Primary Use | Max Flow | Minimum Spanning Tree |
| Data Structure | Residual Graph | Priority Queue |
| Approach | Iterative Improvement | Greedy Growth |
| Graph Type | Directed | Undirected |
| Key Feature | Augmenting Paths | Local Optimization |

### 💡 Implementation Best Practices

### 🎯 General Tips

-   Validate input graphs
-   Handle edge cases
-   Use efficient data structures
-   Consider performance optimizations

### ⚠️ Common Pitfalls

-   Incorrect flow updates
-   Memory management issues
-   Infinite loops
-   Edge weight handling
# 🔍 Substring Search Algorithms Guide

## 📘 Introduction

Substring search algorithms are fundamental techniques for finding pattern matches within text. These algorithms are essential for:

-   📝  **Text Processing**: Finding words or patterns in documents
-   🔎  **Search Engines**: Locating specific content
-   🧬  **DNA Sequence Analysis**: Finding genetic patterns
-   📚  **Plagiarism Detection**: Identifying text matches
-   🔄  **Data Validation**: Pattern matching in strings

## 🔍 Basic Search Algorithms

### 1️⃣ Brute Force Search

A straightforward approach that checks every possible position in the text.

### 📊 Properties

-   ✅ Simple implementation
-   ✅ No preprocessing required
-   ✅ Works with any pattern
-   🔄 Time: O(mn)
-   💾 Space: O(1)

### 💡 Best Used For:

-   Short patterns
-   Short texts
-   Simple implementations
-   When preprocessing overhead isn't worth it
-   When pattern varies frequently
````java
public static List<Integer> bruteForce(CharSequence pattern, CharSequence text,
                                     CharacterComparator comparator) {
    if (pattern == null || pattern.length() == 0) {
        throw new IllegalArgumentException("Pattern cannot be null or empty");
    }
    if (text == null || comparator == null) {
        throw new IllegalArgumentException("Text and comparator cannot be null");
    }

    List<Integer> matches = new ArrayList<>();
    int n = text.length();
    int m = pattern.length();

    // Check each possible position in text
    for (int i = 0; i <= n - m; i++) {
        boolean found = true;
        // Check pattern match starting at position i
        for (int j = 0; j < m; j++) {
            if (comparator.compare(pattern.charAt(j), 
                                 text.charAt(i + j)) != 0) {
                found = false;
                break;
            }
        }
        if (found) {
            matches.add(i);
        }
    }
    return matches;
}
````
### 🔑 Key Tips:

-   Early termination on mismatch
-   Handle edge cases properly
-   Consider text/pattern lengths
-   Validate inputs carefully

### 2️⃣ Rabin-Karp Algorithm

Uses hashing to find exact pattern matches in text.

### 📊 Properties

-   ✅ Efficient for multiple patterns
-   ✅ Rolling hash function
-   ✅ Good average case
-   🔄 Time: Average O(n+m), Worst O(mn)
-   💾 Space: O(1)

### 💡 Best Used For:

-   Multiple pattern matching
-   Long texts
-   Pattern finding in streams
-   Plagiarism detection
-   When preprocessing pattern is beneficial
````java
public static List<Integer> rabinKarp(CharSequence pattern, CharSequence text,
                                    CharacterComparator comparator) {
    if (pattern == null || pattern.length() == 0) {
        throw new IllegalArgumentException("Pattern cannot be null or empty");
    }
    if (text == null || comparator == null) {
        throw new IllegalArgumentException("Text and comparator cannot be null");
    }

    List<Integer> matches = new ArrayList<>();
    int m = pattern.length();
    int n = text.length();
    
    if (m > n) return matches;

    // Calculate pattern hash and first window hash
    int base = 113;  // Prime base
    int patternHash = 0;
    int windowHash = 0;
    int highestPow = 1;

    // Calculate highest power of base needed
    for (int i = 0; i < m - 1; i++) {
        highestPow = highestPow * base;
    }

    // Calculate initial hashes
    for (int i = 0; i < m; i++) {
        patternHash = patternHash * base + pattern.charAt(i);
        windowHash = windowHash * base + text.charAt(i);
    }

    // Slide window and check matches
    for (int i = 0; i <= n - m; i++) {
        if (patternHash == windowHash) {
            // Verify character by character
            boolean match = true;
            for (int j = 0; j < m; j++) {
                if (comparator.compare(pattern.charAt(j), 
                                     text.charAt(i + j)) != 0) {
                    match = false;
                    break;
                }
            }
            if (match) {
                matches.add(i);
            }
        }

        // Calculate hash for next window
        if (i < n - m) {
            windowHash = (windowHash - text.charAt(i) * highestPow) * base
                        + text.charAt(i + m);
        }
    }

    return matches;
}
````
### 🔑 Key Tips:

-   Choose appropriate hash function
-   Handle hash collisions
-   Use efficient rolling hash
-   Consider modulo operations for large texts

### References
[Rabin Karp Algorithm](https://youtu.be/oxd_Z1osgCk?si=Ih9xqcuHlnqcHz5Q)

## 📊 Algorithm Comparison

| Feature | Brute Force | Rabin-Karp |
|---------|------------|------------|
| Time Complexity (Worst) | O(mn) | O(mn) |
| Time Complexity (Average) | O(mn) | O(n+m) |
| Space Complexity | O(1) | O(1) |
| Preprocessing | No | Yes |
| Multiple Patterns | Inefficient | Efficient |
| Implementation | Simple | Moderate |
| Best Case | O(n) | O(n+m) |
| Hash Function | N/A | Yes |

### 💡 Implementation Best Practices

### 🎯 General Tips

-   Validate input parameters
-   Handle edge cases
-   Consider pattern/text lengths
-   Use appropriate data structures

### ⚠️ Common Pitfalls

-   Integer overflow in hash calculation
-   Not handling collisions
-   Inefficient hash updates
-   Missing edge cases
# 🔍 Advanced Substring Search Algorithms

## 📘 Overview

These advanced substring search algorithms use preprocessing for more efficient pattern matching. They are crucial for:

-   🚀  **High Performance Search**: Fast pattern matching
-   📊  **Big Data Analysis**: Processing large text efficiently
-   🔄  **Real-time Matching**: Stream processing
-   📝  **Text Editors**: Efficient find/replace operations
-   🧬  **Bioinformatics**: DNA sequence matching

## 🔍 Advanced Algorithms

### 1️⃣ Knuth-Morris-Pratt (KMP)

An efficient pattern matching algorithm that utilizes a failure table to avoid unnecessary comparisons.

### 📊 Properties

-   ✅ Linear time complexity
-   ✅ Preprocesses pattern
-   ✅ No backward movement in text
-   🔄 Time: O(n + m)
-   💾 Space: O(m)

### 💡 Best Used For:

-   Long patterns
-   Repetitive patterns
-   Streaming data
-   Real-time matching
-   When text cannot be buffered
````java
public static List<Integer> kmp(CharSequence pattern, CharSequence text,
                              CharacterComparator comparator) {
    if (pattern == null || pattern.length() == 0) {
        throw new IllegalArgumentException("Pattern cannot be null or empty");
    }
    if (text == null || comparator == null) {
        throw new IllegalArgumentException("Text and comparator cannot be null");
    }

    List<Integer> matches = new ArrayList<>();
    if (pattern.length() > text.length()) {
        return matches;
    }

    // Build failure table
    int[] failureTable = buildFailureTable(pattern, comparator);
    
    int i = 0;  // text index
    int j = 0;  // pattern index
    
    while (i <= text.length() - pattern.length()) {
        while (j < pattern.length() && 
               comparator.compare(text.charAt(i + j), pattern.charAt(j)) == 0) {
            j++;
        }
        
        if (j == 0) {
            i++;
        } else {
            if (j == pattern.length()) {
                matches.add(i);
            }
            int nextAlignment = failureTable[j - 1];
            i = i + j - nextAlignment;
            j = nextAlignment;
        }
    }
    return matches;
}

public static int[] buildFailureTable(CharSequence pattern, 
                                    CharacterComparator comparator) {
    int[] failureTable = new int[pattern.length()];
    
    int i = 0;
    int j = 1;
    failureTable[0] = 0;
    
    while (j < pattern.length()) {
        if (comparator.compare(pattern.charAt(i), pattern.charAt(j)) == 0) {
            failureTable[j] = i + 1;
            i++;
            j++;
        } else {
            if (i == 0) {
                failureTable[j] = 0;
                j++;
            } else {
                i = failureTable[i - 1];
            }
        }
    }
    
    return failureTable;
}
````
### 🔑 Key Tips:

-   Build failure table efficiently
-   Handle pattern prefixes
-   Avoid backing up in text
-   Consider pattern preprocessing time

### References
[Knuth-Morris-Pratt Algorithm](https://youtu.be/pu2aO_3R118?si=AvU_3RsXi2KdozQh)

### 2️⃣ Boyer-Moore Algorithm

A pattern matching algorithm that uses two heuristics: bad character and good suffix rules.

### 📊 Properties

-   ✅ Sublinear time in practice
-   ✅ Two preprocessing tables
-   ✅ Right-to-left scanning
-   🔄 Time: O(n/m) best, O(mn) worst
-   💾 Space: O(k) where k is alphabet size

### 💡 Best Used For:

-   Long patterns
-   Large alphabets
-   Natural language text
-   When pattern is rare in text
-   When preprocessing time is acceptable
````java
public static List<Integer> boyerMoore(CharSequence pattern, CharSequence text,
                                     CharacterComparator comparator) {
    if (pattern == null || pattern.length() == 0) {
        throw new IllegalArgumentException("Pattern cannot be null or empty");
    }
    if (text == null || comparator == null) {
        throw new IllegalArgumentException("Text and comparator cannot be null");
    }

    List<Integer> matches = new ArrayList<>();
    if (pattern.length() > text.length()) {
        return matches;
    }

    // Build last occurrence table
    Map<Character, Integer> lastTable = buildLastTable(pattern);
    
    int i = 0;
    while (i <= text.length() - pattern.length()) {
        int j = pattern.length() - 1;
        
        // Match pattern from right to left
        while (j >= 0 && 
               comparator.compare(pattern.charAt(j), text.charAt(i + j)) == 0) {
            j--;
        }
        
        if (j == -1) {
            matches.add(i);
            i++;
        } else {
            // Get last occurrence of mismatched character
            char mismatchChar = text.charAt(i + j);
            int lastOccurrence = lastTable.getOrDefault(mismatchChar, -1);
            
            // Calculate shift
            if (lastOccurrence < j) {
                i += j - lastOccurrence;
            } else {
                i++;
            }
        }
    }
    return matches;
}

public static Map<Character, Integer> buildLastTable(CharSequence pattern) {
    Map<Character, Integer> lastTable = new HashMap<>();
    
    // Record last occurrence of each character in pattern
    for (int i = 0; i < pattern.length(); i++) {
        lastTable.put(pattern.charAt(i), i);
    }
    
    return lastTable;
}
````
### 🔑 Key Tips:

-   Implement both heuristics correctly
-   Handle character set efficiently
-   Consider preprocessing overhead
-   Use appropriate shift calculations

### References
[Boyer-Moore Algorithm](https://www.geeksforgeeks.org/boyer-moore-algorithm-for-pattern-searching/)

## 📊 Algorithm Comparison

| Feature | KMP | Boyer-Moore |
|---------|-----|------------|
| Time Complexity (Worst) | O(n + m) | O(mn) |
| Time Complexity (Average) | O(n + m) | O(n/m) |
| Space Complexity | O(m) | O(k) |
| Pattern Scan Direction | Left to Right | Right to Left |
| Preprocessing | Failure Table | Last Occurrence Table |
| Best Case | O(n) | O(n/m) |
| Text Scan Direction | Forward Only | Can Skip Characters |
| Implementation | Moderate | Complex |

### 💡 Implementation Best Practices

### 🎯 General Tips

-   Use efficient preprocessing
-   Handle border cases
-   Consider alphabet size
-   Choose algorithm based on pattern characteristics

### ⚠️ Common Pitfalls

-   Incorrect preprocessing tables
-   Inefficient character comparisons
-   Wrong shift calculations
-   Missing edge cases

### Final Reference to Algorithm Notes
[CS 1332 Data Structures and Algorithms](https://drive.google.com/file/d/1LaF74WE-jMvdlZ0FLwSWRxKVjO75iv8z/view?usp=sharing)
