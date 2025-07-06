# 📚 Insertion in Singly Linked List: Theory, Code & Output

## ✅ 1️⃣ Insertion at the Beginning

**What happens?**  
- The new node becomes the first node of the list.
- Its `next` pointer points to the old head.
- The head pointer is updated to this new node.

**Why use it?**  
- Fastest insertion (**O(1)**) since no traversal is needed.
- Useful for implementing stacks.

**Steps:**
1. Allocate memory for new node.
2. Set `data` and `next`.
3. Update `head` to new node.

**Example:**  
Before:  
head → 10 → 20 → 30 → NULL

Insert `5` → After:  
head → 5 → 10 → 20 → 30 → NULL


---

## ✅ 2️⃣ Insertion at the End

**What happens?**  
- The new node is added after the current last node.

**Why use it?**  
- Used when you want to build a list in insertion order.
- Time complexity **O(n)** (must traverse to the end).

**Steps:**
1. Allocate memory for new node.
2. Set `data` and `next = NULL`.
3. If list is empty, set `head` to new node.
4. Otherwise, traverse to last node and update its `next`.

**Example:**  
Before:  
head → 10 → 20 → 30 → NULL

Insert `40` → After:  
head → 10 → 20 → 30 → 40 → NULL


---

## ✅ 3️⃣ Insertion at a Specific Position (1-based index)

**What happens?**  
- The new node is inserted between existing nodes.

**Why use it?**  
- Flexible insertion anywhere in the list.

**Steps:**
1. Allocate memory for new node.
2. Set `data`.
3. If position is 1, do insertion at beginning.
4. Otherwise:
   - Traverse to `pos-1` node.
   - Check if position is valid.
   - Insert new node by updating pointers.

**Example:**  
Before:  
head → 10 → 20 → 30 → NULL

Insert `15` at position 2 → After:  
head → 10 → 15 → 20 → 30 → NULL


---

## 🚨 Important Notes

- Always check for `malloc` failure.
- Update `head` when inserting at beginning.
- Don’t forget to set new node’s `next`.
- Handle invalid positions gracefully.

---

## ⏱️ Time Complexity

| Operation                | Time Complexity |
|--------------------------|-----------------|
| Insert at beginning      | O(1)            |
| Insert at end            | O(n)            |
| Insert at position k     | O(k)            |

---

## ✅ C Code: Insert at Beginning, End, and Specific Position

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Create new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed.\n");
        exit(1);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Insert at the beginning
void insertAtBeginning(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    newNode->next = *head;
    *head = newNode;
}

// Insert at the end
void insertAtEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

// Insert at a specific position (1-based index)
void insertAtPosition(struct Node** head, int data, int pos) {
    if (pos < 1) {
        printf("Invalid position.\n");
        return;
    }
    if (pos == 1) {
        insertAtBeginning(head, data);
        return;
    }

    struct Node* newNode = createNode(data);
    struct Node* temp = *head;

    for (int i = 1; i < pos - 1 && temp != NULL; i++) {
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Position out of range.\n");
        free(newNode);
        return;
    }

    newNode->next = temp->next;
    temp->next = newNode;
}

// Print the linked list
void printList(struct Node* head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    // Insert nodes at end
    insertAtEnd(&head, 10);
    insertAtEnd(&head, 20);
    insertAtEnd(&head, 40);
    printf("Initial list: ");
    printList(head);

    // Insert at beginning
    insertAtBeginning(&head, 5);
    printf("After inserting 5 at beginning: ");
    printList(head);

    // Insert at position 3
    insertAtPosition(&head, 15, 3);
    printf("After inserting 15 at position 3: ");
    printList(head);

    // Insert at end
    insertAtEnd(&head, 50);
    printf("After inserting 50 at end: ");
    printList(head);

    return 0;
}

OUTPUT:
Initial list: 10 -> 20 -> 40 -> NULL
After inserting 5 at beginning: 5 -> 10 -> 20 -> 40 -> NULL
After inserting 15 at position 3: 5 -> 10 -> 15 -> 20 -> 40 -> NULL
After inserting 50 at end: 5 -> 10 -> 15 -> 20 -> 40 -> 50 -> NULL
