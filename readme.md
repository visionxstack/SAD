# Mock Questions — Full Q&A (Algorithms, Arrays, Pointers, ADTs, Linked Lists)

---

## Introduction to Algorithms

### 1. What is an algorithm? Provide an example.
**A:** An algorithm is a finite, step-by-step set of instructions designed to solve a specific problem or perform a task.

**Example:** A recipe to make tea — boil water, add tea leaves, add milk/sugar, strain, serve. Each step is clear and leads to a defined result.

---

### 2. Explain the characteristics of a good algorithm.
**A:** A good algorithm should have:
- **Input** — takes zero or more well-defined inputs
- **Output** — produces at least one well-defined output
- **Finiteness** — must terminate after a finite number of steps
- **Definiteness** — each step must be clear and unambiguous
- **Effectiveness** — steps must be simple enough to be carried out
- **Efficiency** — should use minimum time and memory

---

### 3. Differentiate between time complexity and space complexity.
**A:**

| Time Complexity | Space Complexity |
|---|---|
| Measures how the **running time** of an algorithm grows with input size | Measures how much **memory** an algorithm needs as input size grows |
| Expressed using Big-O notation (e.g., O(n)) | Also expressed using Big-O notation |
| Focuses on speed/performance | Focuses on memory usage |

---

### 4. What is Big-O notation, and why is it important?
**A:** Big-O notation describes the **upper bound (worst-case growth rate)** of an algorithm's time or space requirement as the input size increases.

**Why important:** It allows us to compare algorithms independent of hardware or programming language, and helps predict how an algorithm will perform as data grows larger.

---

### 5. Describe the difference between an iterative and a recursive algorithm.
**A:**

| Iterative | Recursive |
|---|---|
| Uses loops (`for`, `while`) to repeat steps | Function calls itself to repeat steps |
| Generally uses less memory | Uses more memory due to function call stack |
| Can be harder to read for complex problems | Often cleaner/shorter code for problems like tree traversal |

---

### 6. Explain the significance of worst-case, best-case, and average-case time complexities.
**A:**
- **Best case** — minimum time taken, occurs with the most favorable input
- **Worst case** — maximum time taken, occurs with the most unfavorable input
- **Average case** — expected time taken over all possible typical inputs

**Significance:** Worst-case is most commonly used because it gives a **guarantee** on performance — the algorithm will never take longer than this, no matter the input.

---

### 7. What is a brute-force algorithm? Give an example.
**A:** A brute-force algorithm solves a problem by trying **all possible solutions** directly, without any optimization, until the correct one is found.

**Example:** Searching for two numbers in an array that sum to a target value by checking every possible pair — O(n²).

---

### 8. How does a divide-and-conquer algorithm work? Provide an example.
**A:** Divide-and-conquer works in three steps:
1. **Divide** the problem into smaller sub-problems
2. **Conquer** by solving each sub-problem recursively
3. **Combine** the sub-solutions to form the final answer

**Example:** Merge Sort — splits an array into halves, sorts each half recursively, then merges the sorted halves back together.

---

### 9. Explain the difference between deterministic and non-deterministic algorithms.
**A:**

| Deterministic | Non-Deterministic |
|---|---|
| For a given input, always produces the **same output** following the same steps | May produce **different outcomes** or explore multiple paths for the same input |
| Predictable and used in most real-world programs | Often theoretical, used in complexity theory (e.g., NP problems) |

---

### 10. What are greedy algorithms, and where are they used?
**A:** A greedy algorithm makes the **locally optimal choice** at each step, hoping this leads to a globally optimal solution. It never reconsiders previous choices.

**Used in:** Coin change problems, Dijkstra's shortest path algorithm, Huffman coding, and Minimum Spanning Tree algorithms (Kruskal's/Prim's).

---

## Arrays

### 11. What is an array, and how is it stored in memory?
**A:** An array is a collection of elements of the **same data type**, stored under a single variable name and accessed using an index. Arrays are stored in **contiguous (continuous) memory locations**, meaning each element is placed right next to the previous one, allowing the address of any element to be calculated instantly:
```
address = base_address + (index × size_of_type)
```

---

### 12. How do you declare and initialize an array in C++?
**A:**
```cpp
// Declaration only
int arr[5];

// Declaration + Initialization together
int arr[5] = {10, 20, 30, 40, 50};

// Element-by-element initialization after declaration
int arr[5];
arr[0] = 10;
arr[1] = 20;
arr[2] = 30;
arr[3] = 40;
arr[4] = 50;
```

---

### 13. Explain the difference between a one-dimensional and a multi-dimensional array.
**A:**

| One-Dimensional Array | Multi-Dimensional Array |
|---|---|
| Stores elements in a single row/list | Stores elements in rows and columns (or more dimensions) |
| Declared as `int arr[5];` | Declared as `int arr[3][4];` (2D example) |
| Used for simple lists of data | Used for tables, matrices, grids |

---

### 14. What are the advantages and disadvantages of using arrays?
**A:**

**Advantages:**
- Fast access to elements using index — O(1)
- Simple and easy to use
- Memory efficient (no extra pointer overhead)

**Disadvantages:**
- Fixed size (in static arrays) — cannot grow/shrink easily
- Insertion and deletion are costly — O(n) due to shifting
- Wastes memory if declared larger than needed

---

### 15. How can you insert an element into an array? What is its time complexity?
**A:** To insert an element at a specific position, all elements from that position onward must first be **shifted one step to the right** to create an empty slot, since array memory is contiguous. The new element is then placed into that empty slot.

**Example:**
```
Original: 10  20  40  50
Insert 30:
Step 1 (shift right): 10  20  40  40  50
Step 2 (insert 30):   10  20  30  40  50
```

**Time Complexity: O(n)** — because in the worst case, almost all elements may need to be shifted.

---

### 16. Describe the process of deleting an element from an array.
**A:** To delete an element, we first remove the target element, then **shift all elements after it one step to the left** to fill the gap, keeping the array contiguous.

**Example:**
```
Original: 10  20  30  40  50
Delete 30 (index 2):
Shift left: 10  20  40  50
```

**Time Complexity: O(n)** — because elements after the deleted one must be shifted.

---

### 17. What is the difference between static and dynamic arrays?
**A:**

| Static Array | Dynamic Array |
|---|---|
| Size is fixed at compile time | Size can grow/shrink at runtime |
| Declared as `int arr[5];` | Created using `new` (e.g., `int* arr = new int[5];`) or `vector` |
| Memory allocated on the stack | Memory allocated on the heap |
| Cannot be resized | Can be resized as needed |

---

### 18. How do you find the largest and smallest elements in an array?
**A:** Traverse the array once, keeping track of the maximum and minimum values seen so far.

```cpp
int arr[5] = {10, 45, 3, 67, 22};
int largest = arr[0], smallest = arr[0];

for (int i = 1; i < 5; i++) {
    if (arr[i] > largest) largest = arr[i];
    if (arr[i] < smallest) smallest = arr[i];
}
```
**Time Complexity: O(n)** — single pass through the array.

---

### 19. Write a program to reverse an array in C++.
**A:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int start = 0, end = 4;

    while (start < end) {
        swap(arr[start], arr[end]);
        start++;
        end--;
    }

    for (int i = 0; i < 5; i++)
        cout << arr[i] << " ";

    return 0;
}
// Output: 50 40 30 20 10
```

---

### 20. How is an array different from a linked list?
**A:**

| Array | Linked List |
|---|---|
| Fixed size (static) | Dynamic size |
| Stored in contiguous memory | Stored in scattered memory, connected via pointers |
| Fast access — O(1) | Slow access — O(n) |
| Costly insertion/deletion | Easy insertion/deletion |

---

## Pointers

### 21. What is a pointer in C++, and how is it declared?
**A:** A pointer is a variable that stores the **memory address** of another variable, rather than the value itself.

**Declaration:**
```cpp
int *ptr;   // ptr can store the address of an integer variable
```

---

### 22. Explain the relationship between pointers and arrays.
**A:** The name of an array acts as a pointer to its **first element**. So `arr` is equivalent to `&arr[0]`. This means array elements can be accessed using either indexing or pointer arithmetic:
```cpp
arr[i] == *(arr + i)
```

---

### 23. How do you dynamically allocate memory using pointers in C++?
**A:** Using the `new` keyword:
```cpp
int *ptr = new int;        // single integer
int *arr = new int[5];     // array of 5 integers
```
This allocates memory on the **heap** at runtime, rather than at compile time.

---

### 24. What are pointer arithmetic operations? Provide examples.
**A:** Pointer arithmetic allows moving a pointer forward or backward based on the size of the data type it points to.

```cpp
int arr[5] = {10, 20, 30, 40, 50};
int *ptr = arr;

cout << *(ptr + 1);   // 20 (moves 1 int forward)
ptr++;                 // now points to arr[1]
ptr--;                 // moves back to arr[0]
```

---

### 25. What is a null pointer, and how is it used?
**A:** A null pointer is a pointer that does not point to any valid memory location. It's declared using `nullptr` (or `NULL` in older C++):
```cpp
int *ptr = nullptr;
```
It is used to indicate that a pointer currently has **no valid address**, and is often checked before using a pointer to avoid errors.

---

### 26. How do you pass a pointer to a function in C++?
**A:**
```cpp
void update(int *ptr) {
    *ptr = 100;
}

int main() {
    int x = 10;
    update(&x);   // pass address of x
    cout << x;    // output: 100
}
```
This allows the function to directly modify the original variable, since it works with the actual memory address.

---

### 27. What is a dangling pointer, and how can it be avoided?
**A:** A dangling pointer is a pointer that points to a memory location that has already been **freed or deleted**, but the pointer itself still holds that (now invalid) address.

**How to avoid:** Set the pointer to `nullptr` immediately after deleting the memory it points to:
```cpp
int *ptr = new int;
delete ptr;
ptr = nullptr;   // avoids dangling pointer
```

---

### 28. Explain the concept of double pointers.
**A:** A double pointer is a pointer that stores the **address of another pointer**, rather than the address of a normal variable.

```cpp
int x = 10;
int *ptr = &x;
int **pptr = &ptr;   // pptr is a double pointer

cout << **pptr;   // dereference twice to get value of x → 10
```

---

### 29. How do you deallocate memory allocated using pointers in C++?
**A:** Using the `delete` keyword (matching how it was allocated with `new`):
```cpp
int *ptr = new int;
delete ptr;          // deallocate single variable

int *arr = new int[5];
delete[] arr;         // deallocate array (note the [])
```
This is important to prevent **memory leaks**.

---

### 30. What are the advantages and disadvantages of using pointers?
**A:**

**Advantages:**
- Allow dynamic memory allocation
- Enable efficient array/string handling
- Allow functions to modify original variables (pass by reference)
- Essential for building data structures like linked lists, trees

**Disadvantages:**
- Can cause memory leaks if not deallocated properly
- Risk of dangling pointers and null pointer errors
- More complex and harder to debug
- Can cause program crashes if misused

---

## Abstract Data Types (ADTs)

### 31. What is an Abstract Data Type (ADT)?
**A:** An ADT is a data type defined by its **behavior (operations)** rather than its internal implementation. It specifies *what* operations can be performed, not *how* they are implemented.

**Example:** A Stack ADT defines `push`, `pop`, `peek` — without specifying whether it's implemented using an array or a linked list.

---

### 32. Explain the importance of ADTs in software development.
**A:** ADTs are important because they:
- Separate the **interface** (what it does) from the **implementation** (how it does it)
- Improve code organization and reusability
- Allow implementation to change without affecting code that uses the ADT
- Support encapsulation and abstraction principles

---

### 33. Differentiate between an ADT and a data structure.
**A:**

| ADT | Data Structure |
|---|---|
| A logical/conceptual model — **what** operations are available | The actual **implementation** — how data is stored and manipulated |
| Example: Stack ADT (push, pop) | Example: Stack implemented using an array or linked list |

---

### 34. What are the key operations of a Stack ADT?
**A:**
- **push()** — add an element to the top
- **pop()** — remove the element from the top
- **peek()/top()** — view the top element without removing it
- **isEmpty()** — check if the stack has no elements

---

### 35. How is a Queue ADT different from a Stack ADT?
**A:**

| Stack ADT | Queue ADT |
|---|---|
| LIFO (Last In, First Out) | FIFO (First In, First Out) |
| Operations: push, pop (same end) | Operations: enqueue, dequeue (opposite ends) |

---

### 36. What are the advantages of using ADTs in programming?
**A:**
- Hides implementation details (abstraction)
- Makes code more modular and maintainable
- Allows code reuse across different implementations
- Reduces complexity for the programmer using the ADT

---

### 37. Explain the List ADT and its operations.
**A:** A List ADT represents an ordered collection of elements that can grow or shrink dynamically.

**Key operations:**
- `insert(element, position)` — add an element at a given position
- `delete(position)` — remove an element from a given position
- `get(position)` — retrieve an element at a given position
- `size()` — return the number of elements

---

### 38. How is a Set ADT different from an Array?
**A:**

| Set ADT | Array |
|---|---|
| Does **not allow duplicate** elements | Can contain duplicate values |
| Usually **unordered** | Maintains order based on index |
| Operations focus on membership (add, remove, contains) | Operations focus on index-based access |

---

### 39. Give a real-world example where an ADT is used.
**A:** A **Queue ADT** is used in a printer's task scheduling system — print jobs are added to the queue as they arrive and are printed in the same order (FIFO), ensuring fairness regardless of how the queue is actually implemented internally.

---

### 40. Why is encapsulation important in defining an ADT?
**A:** Encapsulation hides the internal implementation details of the ADT and only exposes the necessary operations to the user. This protects the data from unintended interference, allows the internal implementation to be changed without affecting other code, and makes the ADT safer and easier to use correctly.

---

## Linked Lists

### 41. What is a linked list, and how is it different from an array?
**A:** A linked list is a linear data structure made of nodes, where each node contains data and a pointer to the next node. Unlike arrays, linked list nodes are **not stored in contiguous memory** — they are connected using pointers.

| Array | Linked List |
|---|---|
| Contiguous memory | Scattered memory, linked via pointers |
| Fixed size | Dynamic size |
| Fast access — O(1) | Slow access — O(n) |
| Costly insertion/deletion | Easy insertion/deletion |

---

### 42. Explain the structure of a singly linked list.
**A:** In a singly linked list, each node has two parts:
```cpp
struct Node {
    int data;      // stores the value
    Node* next;    // stores address of the next node
};
```
Each node points only to the **next** node (one direction). The last node's `next` is `NULL`, marking the end of the list.

---

### 43. How do you insert a node at the beginning of a linked list?
**A:**
```cpp
struct Node {
    int data;
    Node* next;
};

void insertAtBeginning(Node*& head, int value) {
    Node* newNode = new Node();
    newNode->data = value;
    newNode->next = head;   // point new node to old head
    head = newNode;          // update head to new node
}
```
**Time Complexity: O(1)** — no shifting required, just pointer updates.

---

### 44. Describe the steps to delete a node from a linked list.
**A:**
1. Traverse the list to find the node to delete and keep track of the **previous node**
2. Update the previous node's `next` pointer to skip over the node being deleted (point it to the deleted node's `next`)
3. Free the memory of the deleted node using `delete`

```cpp
void deleteNode(Node*& head, int key) {
    Node* temp = head;
    Node* prev = nullptr;

    if (temp != nullptr && temp->data == key) {
        head = temp->next;
        delete temp;
        return;
    }

    while (temp != nullptr && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    prev->next = temp->next;
    delete temp;
}
```

---

### 45. What is a doubly linked list, and how does it differ from a singly linked list?
**A:** A doubly linked list is a linked list where each node has **two pointers** — one pointing to the next node and one pointing to the previous node.

```cpp
struct Node {
    int data;
    Node* next;
    Node* prev;
};
```

| Singly Linked List | Doubly Linked List |
|---|---|
| One pointer (`next`) | Two pointers (`next` and `prev`) |
| Traversal in one direction only | Traversal in both directions |
| Uses less memory | Uses more memory (extra pointer) |

---

### 46. How can you detect a cycle in a linked list?
**A:** Using **Floyd's Cycle Detection Algorithm** (also called the "tortoise and hare" method): use two pointers, one moving one step at a time (slow) and one moving two steps at a time (fast). If there is a cycle, the fast pointer will eventually meet the slow pointer. If the fast pointer reaches `NULL`, there is no cycle.

```cpp
bool hasCycle(Node* head) {
    Node* slow = head;
    Node* fast = head;

    while (fast != nullptr && fast->next != nullptr) {
        slow = slow->next;
        fast = fast->next->next;
        if (slow == fast)
            return true;   // cycle detected
    }
    return false;   // no cycle
}
```

---

### 47. Write a program to reverse a linked list in C++.
**A:**
```cpp
struct Node {
    int data;
    Node* next;
};

Node* reverseList(Node* head) {
    Node* prev = nullptr;
    Node* current = head;
    Node* next = nullptr;

    while (current != nullptr) {
        next = current->next;   // save next node
        current->next = prev;   // reverse the pointer
        prev = current;          // move prev forward
        current = next;          // move current forward
    }

    return prev;   // new head of reversed list
}
```

---

### 48. What are the advantages of using linked lists over arrays?
**A:**
- Dynamic size — can grow or shrink at runtime
- Efficient insertion and deletion — O(1) if position is known (no shifting needed)
- No memory wastage from over-allocating, unlike static arrays

---

### 49. How do you implement a queue using a linked list?
**A:** Maintain two pointers, `front` and `rear`. Enqueue adds a node at `rear`; dequeue removes a node from `front`.

```cpp
struct Node {
    int data;
    Node* next;
};

struct Queue {
    Node* front;
    Node* rear;
};

void enqueue(Queue &q, int value) {
    Node* newNode = new Node();
    newNode->data = value;
    newNode->next = nullptr;

    if (q.rear == nullptr) {
        q.front = q.rear = newNode;
        return;
    }
    q.rear->next = newNode;
    q.rear = newNode;
}

void dequeue(Queue &q) {
    if (q.front == nullptr) return;

    Node* temp = q.front;
    q.front = q.front->next;

    if (q.front == nullptr)
        q.rear = nullptr;

    delete temp;
}
```

---

### 50. Explain the difference between a circular linked list and a singly linked list.
**A:**

| Singly Linked List | Circular Linked List |
|---|---|
| Last node's `next` points to `NULL` | Last node's `next` points back to the **first node** |
| Traversal ends at the last node | Traversal can continue indefinitely in a loop |
| Used for simple linear sequences | Used in applications like round-robin scheduling, circular buffers |
