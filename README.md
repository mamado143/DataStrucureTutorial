Data structures are fundamental concepts in computer science and software development. They are ways to organize and store data efficiently to enable easy access, modification, and management. Understanding data structures is essential for writing efficient algorithms and solving complex problems.

Here's an overview of common data structures, organized by category:

1\. **Linear Data Structures**
------------------------------

Linear data structures store data sequentially. The elements are arranged in a linear order, where each element has a successor and/or a predecessor.

### i. **Arrays**

An array is a collection of elements, each identified by an index or key, stored in contiguous memory locations.

-   **Characteristics**:

    -   Fixed size (in most languages).
    -   Random access of elements using an index.
    -   Insertion and deletion are costly (O(n) time complexity).
-   **Use Cases**: Storing fixed-size collections of similar items.

-   **Example (in Python)**:

    python

    Copy

    ```
    array = [1, 2, 3, 4, 5]
    print(array[2])  # Output: 3

    ```

### ii. **Linked Lists**

A linked list is a collection of nodes, where each node contains the data and a reference (or a link) to the next node in the sequence.

-   **Types**:

    -   **Singly Linked List**: Each node points to the next node.
    -   **Doubly Linked List**: Each node points to both the next and previous nodes.
-   **Characteristics**:

    -   Dynamic size (can grow or shrink).
    -   Insertion and deletion are efficient (O(1) at the ends).
    -   Random access is not possible (O(n) to traverse).
-   **Use Cases**: Efficient insertions/deletions at the start or end of a list.

-   **Example (in Python)**:

    python

    Copy

    ```
    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None

    class LinkedList:
        def __init__(self):
            self.head = None

        def append(self, data):
            new_node = Node(data)
            if not self.head:
                self.head = new_node
            else:
                current = self.head
                while current.next:
                    current = current.next
                current.next = new_node

    ll = LinkedList()
    ll.append(1)
    ll.append(2)

    ```

### iii. **Stacks**

A stack is a collection of elements that follows the **LIFO** (Last In, First Out) principle. Elements can be added or removed only from the top.

-   **Operations**:

    -   `push`: Add an element to the top of the stack.
    -   `pop`: Remove the element from the top of the stack.
    -   `peek`: View the top element without removing it.
-   **Use Cases**:

    -   Function call management.
    -   Undo/redo functionality.
    -   Parsing expressions.
-   **Example (in Python)**:

    python

    Copy

    ```
    stack = []
    stack.append(10)  # push
    stack.append(20)
    top = stack.pop()  # pop (returns 20)

    ```

### iv. **Queues**

A queue is a collection of elements that follows the **FIFO** (First In, First Out) principle. Elements are added from the rear and removed from the front.

-   **Operations**:

    -   `enqueue`: Add an element to the rear.
    -   `dequeue`: Remove an element from the front.
-   **Use Cases**:

    -   Task scheduling (e.g., printer queues).
    -   Breadth-first search in graphs.
-   **Example (in Python)**:

    python

    Copy

    ```
    from collections import deque
    queue = deque()
    queue.append(10)  # enqueue
    queue.append(20)
    first = queue.popleft()  # dequeue (returns 10)

    ```

2\. **Non-Linear Data Structures**
----------------------------------

Non-linear data structures do not store data sequentially. Instead, they organize data in a hierarchical or interconnected manner.

### i. **Trees**

A tree is a hierarchical data structure consisting of nodes connected by edges. The top node is called the root, and every node (except the root) has a parent and zero or more children.

-   **Types**:

    -   **Binary Tree**: Each node has at most two children.
    -   **Binary Search Tree (BST)**: A binary tree where the left child is smaller than the parent, and the right child is larger.
    -   **AVL Tree**: A self-balancing BST.
    -   **Heap**: A binary tree where the parent node is either greater than or smaller than its children (min-heap, max-heap).
-   **Use Cases**:

    -   Representing hierarchical relationships (e.g., file systems).
    -   Efficient searching and sorting (BST).
-   **Example (Binary Tree in Python)**:

    python

    Copy

    ```
    class TreeNode:
        def __init__(self, value):
            self.value = value
            self.left = None
            self.right = None

    root = TreeNode(10)
    root.left = TreeNode(5)
    root.right = TreeNode(15)

    ```

### ii. **Graphs**

A graph is a collection of nodes (vertices) connected by edges. It can be directed or undirected.

-   **Characteristics**:

    -   **Vertices**: The entities in the graph.
    -   **Edges**: The connections between the vertices.
-   **Types**:

    -   **Directed Graph**: Edges have a direction (A → B).
    -   **Undirected Graph**: Edges do not have direction (A --- B).
    -   **Weighted Graph**: Edges have weights or costs.
-   **Use Cases**:

    -   Representing networks (social networks, transportation systems).
    -   Algorithms like Dijkstra's for shortest path, Depth First Search (DFS), and Breadth First Search (BFS).
-   **Example (Graph in Python using Adjacency List)**:

    python

    Copy

    ```
    graph = {
        'A': ['B', 'C'],
        'B': ['A', 'D', 'E'],
        'C': ['A', 'F'],
        'D': ['B'],
        'E': ['B', 'F'],
        'F': ['C', 'E']
    }

    ```

3\. **Hash-based Structures**
-----------------------------

### i. **Hash Tables (Hash Maps)**

A hash table stores key-value pairs, where each key is mapped to a value using a hash function. Hash tables provide efficient lookups, insertions, and deletions.

-   **Operations**:

    -   `insert(key, value)`: Insert a key-value pair.
    -   `get(key)`: Retrieve the value associated with the key.
    -   `delete(key)`: Remove the key-value pair.
-   **Use Cases**:

    -   Caching.
    -   Databases (indexing).
    -   Implementing sets.
-   **Example (in Python)**:

    python

    Copy

    ```
    hash_map = {}
    hash_map["name"] = "Alice"
    print(hash_map["name"])  # Output: Alice

    ```

4\. **Advanced Data Structures**
--------------------------------

### i. **Trie (Prefix Tree)**

A Trie is a tree-like data structure used to store strings or sequences, where each node represents a character of the string.

-   **Use Cases**:

    -   Autocomplete functionality.
    -   Spell checkers.
    -   Searching for prefixes.
-   **Example (in Python)**:

    python

    Copy

    ```
    class TrieNode:
        def __init__(self):
            self.children = {}
            self.is_end_of_word = False

    class Trie:
        def __init__(self):
            self.root = TrieNode()

        def insert(self, word):
            node = self.root
            for char in word:
                if char not in node.children:
                    node.children[char] = TrieNode()
                node = node.children[char]
            node.is_end_of_word = True

    trie = Trie()
    trie.insert("hello")

    ```

* * * * *

Time Complexities Summary
-------------------------

Here's a summary of time complexities for common operations on these data structures:

| Data Structure | Access | Search | Insertion | Deletion |
| --- | --- | --- | --- | --- |
| Array | O(1) | O(n) | O(n) | O(n) |
| Linked List | O(n) | O(n) | O(1) | O(1) |
| Stack | O(n) | O(n) | O(1) | O(1) |
| Queue | O(n) | O(n) | O(1) | O(1) |
| Binary Search Tree | O(log n) | O(log n) | O(log n) | O(log n) |
| Hash Table | O(1) | O(1) | O(1) | O(1) |

* * * * *

Conclusion
----------

Data structures are crucial for solving problems efficiently. Choosing the right data structure depends on the problem you're solving and the operations you need to optimize. Mastering these concepts will give you a strong foundation for designing algorithms and building efficient systems.
