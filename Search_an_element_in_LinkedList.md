# 🔎 Searching an Element in a Singly Linked List

## ✅ What is Searching in a Linked List?

Searching means **checking each node** to see if it contains the value (key) you’re looking for.

---

## ✅ Why is Linked List Search Linear?

- Linked lists do **not** store elements in contiguous memory like arrays.
- You can’t jump to an index — you must traverse **node by node** from the head.
- This makes searching a **linear time O(n)** operation.

---

## ✅ How Do You Search in a Linked List?

1️⃣ Start at the `head` node.  
2️⃣ Loop through each node using the `next` pointer.  
3️⃣ For each node:
   - Compare `node->data` with the key.
   - If they match, return the position.
   - Otherwise, move to the next node.
4️⃣ If you reach the end of the list (`NULL`) without a match, the key isn’t in the list.

---

## ✅ How is Position Calculated?

- Initialize `position` to 1 (1-based index).
- Increment `position` every time you move to the next node.
- When you find the key, return the current `position`.

---

## ✅ Edge Cases

✔️ **Empty list** (`head == NULL`): element cannot be found.  
✔️ **Element at head**: fastest case (**O(1)**).  
✔️ **Element at end or missing**: requires traversing the entire list (**O(n)**).

---

## ✅ Time & Space Complexity

| Complexity    | Value                   |
|---------------|-------------------------|
| Time          | O(1) best, O(n) worst   |
| Space         | O(1)                    |

---

## ✅ Example Walkthrough

For the list:
head → 10 → 20 → 30 → 40 → NULL


🔹 Searching for `30`:  
- Node 1: 10 ≠ 30 → next (position 2)  
- Node 2: 20 ≠ 30 → next (position 3)  
- Node 3: 30 == 30 → found at position 3.

🔹 Searching for `50`:  
- Traverse all nodes → no match → reach NULL → element not found.

---

## ✅ C Code: Search for an Element in a Linked List

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node
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

// Function to search for an element in the linked list
int searchElement(struct Node* head, int key) {
    int position = 1;
    while (head != NULL) {
        if (head->data == key) {
            return position; // Element found
        }
        head = head->next;
        position++;
    }
    return -1; // Element not found
}

// Function to print the linked list
void printList(struct Node* head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    // Create a sample linked list: 10 -> 20 -> 30 -> 40
    head = createNode(10);
    head->next = createNode(20);
    head->next->next = createNode(30);
    head->next->next->next = createNode(40);

    printf("Linked list: ");
    printList(head);

    int key;
    printf("Enter the element to search: ");
    scanf("%d", &key);

    int pos = searchElement(head, key);
    if (pos != -1) {
        printf("Element %d found at position %d.\n", key, pos);
    } else {
        printf("Element %d not found in the list.\n", key);
    }

    return 0;
}

✅ Example Outputs
Case 1: Element present
Linked list: 10 -> 20 -> 30 -> 40 -> NULL
Enter the element to search: 30
Element 30 found at position 3.


Case 2: Element not present
Linked list: 10 -> 20 -> 30 -> 40 -> NULL
Enter the element to search: 50
Element 50 not found in the list.




## ✅ How Does the Code Work?

- `createNode()` dynamically allocates memory for a new node and initializes its `data` and `next` fields.

- `printList()` traverses the linked list from `head` to `NULL`, printing each node’s `data` followed by an arrow.

- `searchElement()` traverses the linked list node by node, comparing each node’s `data` with the search key:
  - If a match is found, it returns the current position (1-based index).
  - If no match is found before reaching the end of the list, it returns `-1` to indicate the key is not present.
