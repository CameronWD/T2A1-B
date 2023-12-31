# T2A1-B 
# Workbook Part 2 

## Question 1
### Identify and explain the workings of TWO sorting algorithms and discuss and compare their performance/efficiency (i.e. Big O) 

#### - Comparison and Non-Comparison Sorts
Two fundamental types of sorting algorithms exist: Comparison and Non-Comparison sorts. Comparison sorts work by performing pairwise comparisons of elements, as seen in Bubble Sort, Merge Sort, and Quick Sort. They are versatile, capable of handling any data type that can be compared. Non-Comparison sorts, such as Counting Sort, Radix Sort, and Bucket Sort, do not use pairwise comparisons but sort values based on specific properties or structural elements, like digital or positional values. 

#### - Quick Sort (Comparison sort)
Quick Sort is a divide-and-conquer algorithm, meaning it partitions data into smaller subsets around a pivot and then recursively sorts these subsets. This approach relies on the algebraic principle of recursion and partitioning, which contributes to its time complexity. The pivot selection significantly impacts the time complexity. In the best and average-case scenarios, when the pivot is the median, the partitioning results in equal halves leading to a time complexity of O(nlogn). This complexity arises because each recursive step divides the problem size by approximately half, and there are log(n) such steps (i.e., nlog(n)). However, if the pivot is the largest or smallest element (worst case), the partition becomes unbalanced, leading to a time complexity of O(n^2). This is because every partition step divides the list into a size n-1 and 1 element, taking n steps to finish, hence nn or n^2. The space complexity is O(log n) because it uses a stack to manage recursive calls, which can pile up to log(n) levels deep.

#### - Counting Sort (Non-Comparison Sort)
Counting Sort sorts elements by counting the occurrences of each unique element, then placing them in order. It operates under the assumption that the input consists of non-negative integers, enabling it to sort using the actual value of the keys. Its time complexity is O(n+k), where 'n' represents the number of elements, and 'k' represents the range of the input data. This linear time complexity arises from the algorithm's ability to sort each element in a single pass rather than by comparison. It iterates over the array 'n' times and then iterates from 0 to 'k' to generate the sorted output. Hence, the time complexity is O(n+k). It has a space complexity of O(n+k) because it requires an auxiliary counting array of size 'k' to hold the count of each element and an output array of size 'n' to hold the sorted elements.

### Sort Algorithm Comparison
Both Quick Sort and Counting Sort have different use cases, and their efficiencies vary based on the data they are applied to. Quick Sort is efficient for larger datasets and when the pivot is near the median, leading to a time complexity of O(nlogn). On the contrary, Counting Sort is efficient when sorting integers with a smaller range, yielding a linear time complexity of O(n+k). While Quick Sort's time complexity could degrade to O(n^2) in worst-case scenarios, Counting Sort remains linear but can consume significant space if 'k' is large. Therefore, the selection between these two would depend on the nature of the problem at hand.

## Question 2
### Identify and explain the workings of TWO search algorithms and discuss and compare their performance/efficiency (i.e. Big O)

#### - Binary Search
Binary Search is a divide-and-conquer search algorithm used on a sorted array to find a target value. It begins by comparing the target value with the middle element of the array. If the target value matches the middle element, its position is returned. This best-case scenario has a time complexity of O(1), meaning that the search could potentially be resolved in a single operation if the target value is at the center of the array. However, if the target value is greater or less than the middle element, the search continues in the corresponding half of the array. For example, if the target value is greater than the middle element, the process is repeated in the half of the array that is greater than the original middle element. This process, which effectively eliminates half of the dataset each time, continues until the target value is found or the subarray reduces to zero. The worst and average case for time complexity is O(log n), as each comparison eliminates half of the elements in the array. Logarithmic time complexity is particularly efficient because the amount of data that the algorithm needs to process decreases exponentially with each operation. This makes Binary Search highly efficient for large datasets. Regarding space complexity, it is O(1) in an iterative implementation and O(log n) in a recursive one, reflecting the resources needed to manage the data.

#### - Breadth-First Search (BFS)
Breadth-First Search (BFS), a type of graph traversal algorithm, explores all the vertices of a graph in breadth-first order. This means that for a given search, BFS explores all vertices at the current depth before moving onto the next level. It employs a queue data structure, enqueuing the starting vertex and its adjacent vertices, then dequeues each vertex, processes it, and enqueues the unvisited adjacent nodes. This algorithm has a time complexity of O(V+E) where “V” is the number of vertices and “E” is the number of edges, accounting for the worst-case scenario where each vertex and edge of the graph is explored. This linear time complexity means that as the size of the input (the graph) increases, the time it takes for the algorithm to process it increases proportionally. The space complexity of BFS is O(V), as it needs to keep track of all vertices at worst. This is because in the worst-case scenario, all nodes would have to be held in the queue simultaneously, particularly if the graph is a tree structure. 

#### - Search Algorithm Comparison
Comparison of Big-O Binary Search and BFS have different use cases, and their efficiency depends on the nature of the problem at hand. Binary Search, which has a time complexity of O(log n), is used for searching a sorted array or list, making it a highly efficient search algorithm for such tasks. For example, Binary Search is often employed in database searches where records are typically sorted by ID or other specific fields. On the other hand, BFS is more suited for graph traversal or finding the shortest path in unweighted graphs. Examples of its application include its use in GPS navigation systems to locate nearby positions, or by web crawlers in search engines. While these search methods have differing Big-O values, they each have scenarios where they are the most ideal algorithm.

## References 
Cormen, T. H., Charles Eric Leiserson, Rivest, R. L., & Stein, C. (2022). Introduction to algorithms. The Mit Press.

Donald Ervin Knuth. (1977). The art of computer programming. 1 Fundamental algorithms. Reading, Mass. Addison-Wesley.

GeeksforGeeks. (2014, January 7). QuickSort - GeeksforGeeks. GeeksforGeeks; GeeksforGeeks. https://www.geeksforgeeks.org/quick-sort/

GeeksforGeeks. (2019, April). Binary Search - GeeksforGeeks. GeeksforGeeks. https://www.geeksforgeeks.org/binary-search/