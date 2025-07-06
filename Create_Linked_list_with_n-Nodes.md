# 📚 Creating a Linked List with n Nodes

## ✅ Theory: How to Create a Linked List with n Nodes

1️⃣ **Define the Node Structure**  
- Create a `struct Node` with two members:
  - `data`: stores the value of the node.
  - `next`: a pointer to the next node.

2️⃣ **Decide the Number of Nodes**  
- Ask the user for `n`, the number of nodes to create.

3️⃣ **Create the First Node (Head)**
- Allocate memory for the first node using `malloc()`.
- Set its `data` field with user input.
- Point its `next` to `NULL` initially.
- Save its address as the `head` of the list.

4️⃣ **Create Remaining Nodes**
- Loop from 2 to `n`:
  - For each node:
    - Allocate memory for the new node.
    - Set its `data` field with user input.
    - Point its `next` to `NULL`.
    - Link the previous node’s `next` to this new node.
    - Move the temporary pointer to the new node.

5️⃣ **Traverse the List**
- Start from `head` and move through each node using `next`.
- Print each node’s data until you reach `NULL`.

---

## ✅ C Code: Create Linked List with n Nodes

```c
#include <stdio.h>
#include <stdlib.h>

// Define the node structure
struct Node {
    int data;
    struct Node* next;
};

int main() {
    struct Node *head = NULL, *temp = NULL, *newNode = NULL;
    int n, i, value;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid number of nodes.\n");
        return 0;
    }

    // Step 1: Create the first node (head)
    newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    printf("Enter data for node 1: ");
    scanf("%d", &value);
    newNode->data = value;
    newNode->next = NULL;
    head = newNode;  // first node is head
    temp = head;

    // Step 2: Create remaining nodes
    for (i = 2; i <= n; i++) {
        newNode = (struct Node*)malloc(sizeof(struct Node));
        if (newNode == NULL) {
            printf("Memory allocation failed.\n");
            return 1;
        }
        printf("Enter data for node %d: ", i);
        scanf("%d", &value);
        newNode->data = value;
        newNode->next = NULL;

        temp->next = newNode;  // link previous node to new node
        temp = newNode;        // move temp to new node
    }

    // Step 3: Traverse and print the list
    printf("Linked list: ");
    temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");

    return 0;
}
