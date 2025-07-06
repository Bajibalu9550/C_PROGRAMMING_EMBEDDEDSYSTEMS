# 📚 Linked List

## 🔹 What is a Linked List?
A **linked list** is a linear data structure where elements, called **nodes**, are stored non-contiguously in memory. Each node contains:
1. **Data** – the value you want to store.
2. **Pointer (link)** – a reference to the next node in the list.

---

## 🔹 Types of Linked Lists
✅ **Singly Linked List** – each node points only to the next node.  
✅ **Doubly Linked List** – each node points to both the next *and* previous nodes.  
✅ **Circular Linked List** – the last node points back to the first node, making a circular loop.

---

## 🔹 Basic Operations
- **Insertion** – add a node at the beginning, middle, or end.
- **Deletion** – remove a node.
- **Traversal** – go through each node to access or print data.
- **Search** – find a node with a specific value.

---

## 🔹 Example: Singly Linked List Node in C

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

int main() {
    // Create nodes
    struct Node* head = (struct Node*)malloc(sizeof(struct Node));
    struct Node* second = (struct Node*)malloc(sizeof(struct Node));
    struct Node* third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    // Traverse the list
    struct Node* current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");

    return 0;
}
