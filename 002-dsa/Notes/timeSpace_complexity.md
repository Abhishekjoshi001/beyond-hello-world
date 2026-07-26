# Time And Space Complexity
## Time Complexity
- Time complexity is not the time taken to execute a code
- It is the rate at which the time take increases with respect to the input size
- It represents the relationship between input size and execution time, visualized as a graph where the x-axis is input size, y-axis is time, and the slope indicates the complexity rate.

### Big O Notation
Time complexity uses **Big O notation** to classify algorithms:
- **Worst-case scenario** assumed
- **Constants ignored** (5n treated as n)
- **Lower-order terms ignored** (n² + n treated as n²)

### Common Time Complexities

| Notation | Name | Example |
|----------|------|---------|
| **O(1)** | Constant | `arr[0]` (direct access) |
| **O(log n)** | Logarithmic | Binary search on sorted array |
| **O(n)** | Linear | `for item in arr: print(item)` |
| **O(n log n)** | Linearithmic | Merge sort, Quick sort |
| **O(n²)** | Quadratic | `for i in arr: for j in arr: compare(i,j)` |
| **O(n³)** | Cubic | `for i in arr: for j in arr: for k in arr: process(i,j,k)` |
| **O(2ⁿ)** | Exponential | `def fib(n): return fib(n-1) + fib(n-2)` |
| **O(n!)** | Factorial | Generate all permutations of n elements |

## Space Complexity
- Memory used by an algorithm relative to input size
- Same Big O notation and rules apply
- Includes auxiliary space (temporary variables, recursion stack)

### Common Space Complexities
- **O(1)**: Constant variables
- **O(n)**: Linear arrays
- **O(n²)**: 2D matrices
- **O(log n)**: Recursion depth in binary search
