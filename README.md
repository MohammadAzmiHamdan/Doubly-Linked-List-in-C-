# Doubly Linked List in C++

A reusable **Doubly Linked List** implementation in C++ using **Class Templates**.

This project implements a generic doubly linked list from scratch and provides common operations for inserting, deleting, searching, updating, reversing, and managing nodes.

## Features

The `clsDblLinkedList<T>` class supports:

* Insert at the beginning
* Insert at the end
* Insert after a specific node
* Insert after a specific index
* Find an item
* Delete the first node
* Delete the last node
* Delete a specific node
* Get a node by index
* Get an item by index
* Update an item
* Clear the entire list
* Reverse the list
* Get the current size
* Check whether the list is empty

## Data Structure

Each node contains three components:

```cpp
class Node
{
public:
    T value;
    Node* next;
    Node* prev;
};
```

Unlike a Singly Linked List, each node maintains two connections:

* `next` → points to the next node.
* `prev` → points to the previous node.

This allows traversal in both directions.

## Main Class

```cpp
template <class T>
class clsDblLinkedList
```

Using a template allows the list to store different data types, for example:

```cpp
clsDblLinkedList<int> Numbers;
clsDblLinkedList<string> Names;
```

## Core Operations

### InsertAtBeginning()

Adds a new node at the beginning of the list and updates the `head` pointer.

```cpp
void InsertAtBeginning(T value);
```

### InsertAtEnd()

Adds a new node at the end of the list.

```cpp
void InsertAtEnd(T value);
```

### InsertAfter()

Inserts a new node after a specific node or index.

```cpp
void InsertAfter(Node* current, T value);
bool InsertAfter(int Index, T Value);
```

### Find()

Searches for a node containing a specific value.

```cpp
Node* Find(T Value);
```

Returns the node if found, otherwise returns `NULL`.

### DeleteNode()

Removes a specific node while maintaining the connections between the previous and next nodes.

```cpp
void DeleteNode(Node*& NodeToDelete);
```

### DeleteFirstNode()

Removes the first node and updates the `head`.

```cpp
void DeleteFirstNode();
```

### DeleteLastNode()

Removes the last node from the list.

```cpp
void DeleteLastNode();
```

### Reverse()

Reverses the linked list by swapping the `next` and `prev` pointers of every node.

```cpp
void Reverse();
```

### GetNode()

Returns a node at a specific index.

```cpp
Node* GetNode(int Index);
```

### GetItem()

Returns the value stored at a specific index.

```cpp
T GetItem(short Index);
```

### UpdateItem()

Updates the value of an item at a specific index.

```cpp
bool UpdateItem(short Index, T NewValue);
```

### Clear()

Deletes all nodes from the list.

```cpp
void Clear();
```

## Complexity

| Operation            | Complexity |
| -------------------- | ---------: |
| Insert at Beginning  |       O(1) |
| Insert at End        |       O(n) |
| Find                 |       O(n) |
| Delete First         |       O(1) |
| Delete Last          |       O(n) |
| Delete by Node       |       O(1) |
| Get Node by Index    |       O(n) |
| Get Item by Index    |       O(n) |
| Update Item by Index |       O(n) |
| Reverse              |       O(n) |
| Clear                |       O(n) |

> `DeleteNode()` itself performs the pointer updates in O(1) when the target node is already known. Finding that node first may require O(n).

## Concepts Practiced

* Doubly Linked Lists
* Nodes and Pointers
* Dynamic Memory Allocation
* Templates
* Pointer Manipulation
* Object-Oriented Programming
* Data Structures
* Traversal
* Insertion and Deletion
* Searching
* Index-Based Access
* Reversing Linked Lists
* Time Complexity

## Learning Purpose

This implementation was created as part of my practice with **Data Structures in C++**.

The main goal was to understand how a Doubly Linked List works internally and how operations such as insertion, deletion, and reversal affect the relationships between nodes.

It also provides a reusable foundation that can later be used to build higher-level data structures such as:

* Stack
* Queue
* Deque
* Other custom data structures
