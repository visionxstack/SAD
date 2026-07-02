# C++ DSA Class Test — Questions & Answers

---

## Question 1: Array and Pointer

### a. Theory
**Q: What is an array in C++? Explain why array elements are stored in continuous memory locations.**

**A:** An array is a collection of elements of the **same data type** stored under a single variable name, where each element is accessed using an index.

Array elements are stored in **continuous (contiguous) memory locations** because this allows the compiler to calculate the address of any element instantly using a simple formula:

```
address of arr[i] = base_address + (i × size_of_data_type)
```

This gives **O(1) constant-time access** to any element — no searching is needed, just a direct address calculation. If elements were scattered in memory, this fast indexing would not be possible.

### b. Pointer Concept
**Q: What is the meaning of the following statement? `int *ptr;`**

**A:** This statement declares `ptr` as a **pointer variable** that can store the **memory address** of an integer variable. `ptr` itself does not hold an integer value — it holds the *location* where an integer is stored. To get the value at that address, we use the dereference operator: `*ptr`.

### c. Practical
**Q: Given the array:**
```cpp
int arr[5] = {10, 20, 30, 40, 50};
```
**Write the output of:**
```cpp
cout << arr[2] << endl;
cout << *(arr + 2) << endl;
cout << *(arr + 4) << endl;
```

**A: Output:**
```
30
30
50
```

**Explanation:**
- `arr[2]` → the 3rd element (index starts at 0) → **30**
- `*(arr + 2)` → pointer arithmetic; `arr` points to the first element, so moving 2 steps ahead and dereferencing gives the same result as `arr[2]` → **30**
- `*(arr + 4)` → the 5th element (last one) → **50**

**Key rule:** `arr[i]` and `*(arr + i)` always give the same result, because the array name acts as a pointer to its first element.

---

## Question 2: Structure

### a. Theory
**Q: What is a structure in C++? Why do we use structures?**

**A:** A structure (`struct`) is a user-defined data type in C++ that groups **variables of different data types** together under a single name. Each variable inside a structure is called a **member**.

We use structures because they let us represent a real-world entity — like a Student, Employee, or Book — that has multiple related properties of different types, all bundled together as one logical unit. This makes code more organized, readable, and easier to manage compared to using separate variables for each property.

### b. Concept
**Q: Write the difference between an array and a structure.**

**A:**

| Array | Structure |
|---|---|
| Stores elements of the **same** data type | Stores elements of **different** data types |
| Elements accessed using an **index** (`arr[0]`) | Members accessed using the **dot operator** (`s.rollNo`) |
| Homogeneous collection | Heterogeneous collection |
| Fixed set of similar values | Groups related but different attributes |

### c. Practical
**Q: Create a structure named Student with members: rollNo, name, marks. Write a short C++ program to input and display the details of one student.**

**A:**
```cpp
#include <iostream>
using namespace std;

struct Student {
    int rollNo;
    string name;
    float marks;
};

int main() {
    Student s1;

    cout << "Enter Roll No: ";
    cin >> s1.rollNo;

    cout << "Enter Name: ";
    cin >> s1.name;

    cout << "Enter Marks: ";
    cin >> s1.marks;

    cout << "\n--- Student Details ---" << endl;
    cout << "Roll No: " << s1.rollNo << endl;
    cout << "Name: " << s1.name << endl;
    cout << "Marks: " << s1.marks << endl;

    return 0;
}
```

---

## Question 3: Linked List

### a. Theory
**Q: What is a linked list? How is it different from an array?**

**A:** A linked list is a linear data structure made up of **nodes**, where each node contains two parts: some **data**, and a **pointer** to the next node in the sequence. Unlike an array, the nodes of a linked list are **not stored in contiguous memory** — they can be scattered anywhere in memory, and are connected together using pointers.

**Difference from array:**

| Array | Linked List |
|---|---|
| Fixed size (in most cases) | Dynamic size, grows/shrinks at runtime |
| Stored in contiguous memory | Stored in scattered memory, linked by pointers |
| Fast random access — O(1) | Slow access — O(n), must traverse from start |
| Insertion/deletion is costly (shifting needed) | Insertion/deletion is easy (just update pointers) |

### b. Node Concept
**Q: Explain the purpose of `data` and `next` in the following structure:**
```cpp
struct Node {
    int data;
    Node* next;
};
```

**A:**
- `data` — stores the **actual value** held by that node (e.g., an integer).
- `next` — a pointer that stores the **memory address of the next node** in the list, which is what "links" one node to another. If a node is the last one in the list, its `next` is set to `NULL`, indicating the end of the list.

### c. Practical
**Q: Draw a singly linked list containing the values: `10 -> 20 -> 30 -> NULL`. Also write the C++ code to create these three nodes manually.**

**A: Diagram:**
```
 ┌────┬──────┐    ┌────┬──────┐    ┌────┬──────┐
 │ 10 │  o───┼───>│ 20 │  o───┼───>│ 30 │ NULL │
 └────┴──────┘    └────┴──────┘    └────┴──────┘
  first             second           third
```

**Code:**
```cpp
struct Node {
    int data;
    Node* next;
};

int main() {
    Node* first = new Node();
    Node* second = new Node();
    Node* third = new Node();

    first->data = 10;
    first->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    return 0;
}
```

---

## Question 4: Stack and Queue

### a. Theory
**Q: What is a stack? Explain the meaning of LIFO with an example.**

**A:** A stack is a linear data structure in which insertion and deletion of elements happen only at **one end**, called the **top**. It follows the **LIFO (Last In, First Out)** principle — the last element added is the first one to be removed.

**Example:** A stack of plates on a table. You always place a new plate on **top**, and when you need a plate, you take the one from the **top** first — the plate placed last is removed first.

### b. Theory
**Q: What is a queue? Explain the meaning of FIFO with an example.**

**A:** A queue is a linear data structure in which insertion happens at one end (**rear**) and deletion happens at the other end (**front**). It follows the **FIFO (First In, First Out)** principle — the first element added is the first one to be removed.

**Example:** A line of people waiting at a ticket counter. The first person to join the line (rear) is the first person to get served and leave (front).

### c. Comparison
**Q: Write any three differences between stack and queue.**

**A:**

| Stack | Queue |
|---|---|
| Follows **LIFO** (Last In, First Out) | Follows **FIFO** (First In, First Out) |
| Insertion and deletion happen at the **same end** (top) | Insertion happens at **rear**, deletion happens at **front** |
| Main operations: **push**, **pop** | Main operations: **enqueue**, **dequeue** |

---

## Question 5: Recursion

### a. Theory
**Q: What is recursion in C++?**

**A:** Recursion is a programming technique in which a function calls **itself**, directly or indirectly, to solve a problem by breaking it down into smaller sub-problems of the same type.

### b. Concept
**Q: What is a base condition in recursion? Why is it important?**

**A:** A base condition (or base case) is the condition that stops the recursive function from calling itself further and returns a value directly. It is important because without a base condition, the function would keep calling itself **infinitely**, leading to a **stack overflow** and crashing the program.

### c. Dry Run
**Q: Dry run the following recursive function for `factorial(4)`:**
```cpp
int factorial(int n) {
    if (n == 0)
        return 1;
    return n * factorial(n - 1);
}
```

**A: Dry Run:**

**Calling phase (going down):**
```
factorial(4) = 4 * factorial(3)
factorial(3) = 3 * factorial(2)
factorial(2) = 2 * factorial(1)
factorial(1) = 1 * factorial(0)
factorial(0) = 1        ← base condition reached, stops here
```

**Returning phase (unwinding back up):**
```
factorial(0) = 1
factorial(1) = 1 * 1  = 1
factorial(2) = 2 * 1  = 2
factorial(3) = 3 * 2  = 6
factorial(4) = 4 * 6  = 24
```

### d. Practical
**Q: Write the final answer: factorial(4) = ?**

**A: factorial(4) = 24**
