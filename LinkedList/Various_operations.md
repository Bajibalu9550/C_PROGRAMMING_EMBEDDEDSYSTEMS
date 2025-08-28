# C Program: Recursive Functions for Various Operations on a Single Linked List

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// (i) Find length of the list
int length(struct Node *head) {
    if (head == NULL)
        return 0;
    return 1 + length(head->next);
}

// (ii) Find sum of all elements in the list
int sumList(struct Node *head) {
    if (head == NULL)
        return 0;
    return head->data + sumList(head->next);
}

// (iii) Display the linked list
void displayList(struct Node *head) {
    if (head == NULL) {
        printf("NULL\n");
        return;
    }
    printf("%d -> ", head->data);
    displayList(head->next);
}

// (iv) Display the list in reverse order
void displayReverse(struct Node *head) {
    if (head == NULL)
        return;
    displayReverse(head->next);
    printf("%d -> ", head->data);
}

// (v) Reverse the linked list
struct Node* reverseList(struct Node *head) {
    if (head == NULL || head->next == NULL)
        return head;
    struct Node *rest = reverseList(head->next);
    head->next->next = head;
    head->next = NULL;
    return rest;
}

// (vi) Insert a node at the end of the list
struct Node* insertEnd(struct Node *head, int data) {
    if (head == NULL)
        return createNode(data);
    head->next = insertEnd(head->next, data);
    return head;
}

// (vii) Delete the last node from the list
struct Node* deleteEnd(struct Node *head) {
    if (head == NULL)
        return NULL;
    if (head->next == NULL) {
        free(head);
        return NULL;
    }
    head->next = deleteEnd(head->next);
    return head;
}

// (viii) Search for an element in the list
int searchElement(struct Node *head, int key) {
    if (head == NULL)
        return 0;
    if (head->data == key)
        return 1;
    return searchElement(head->next, key);
}

// Helper function to input a list from user
struct Node* inputList(int n) {
    struct Node *head = NULL;
    int data;
    for (int i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf("%d", &data);
        head = insertEnd(head, data);
    }
    return head;
}

int main() {
    struct Node *head = NULL;
    int n, key;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);
    head = inputList(n);

    printf("Linked list: ");
    displayList(head);

    printf("Length of list: %d\n", length(head));
    printf("Sum of elements: %d\n", sumList(head));

    printf("Linked list in reverse order: ");
    displayReverse(head);
    printf("NULL\n");

    head = reverseList(head);
    printf("Linked list after reversing: ");
    displayList(head);

    printf("Enter an element to insert at the end: ");
    scanf("%d", &key);
    head = insertEnd(head, key);
    printf("List after insertion: ");
    displayList(head);

    head = deleteEnd(head);
    printf("List after deleting last node: ");
    displayList(head);

    printf("Enter an element to search: ");
    scanf("%d", &key);
    if (searchElement(head, key))
        printf("Element %d found in the list.\n", key);
    else
        printf("Element %d not found in the list.\n", key);

    return 0;
}

OUTPUT:
Enter the number of nodes: 3
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 30
Linked list: 10 -> 20 -> 30 -> NULL
Length of list: 3
Sum of elements: 60
Linked list in reverse order: 30 -> 20 -> 10 -> NULL
Linked list after reversing: 30 -> 20 -> 10 -> NULL
Enter an element to insert at the end: 40
List after insertion: 30 -> 20 -> 10 -> 40 -> NULL
List after deleting last node: 30 -> 20 -> 10 -> NULL
Enter an element to search: 20
Element 20 found in the list.
