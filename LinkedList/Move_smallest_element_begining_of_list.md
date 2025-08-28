# C Program to Move the Smallest Element to the Beginning of a Single Linked List

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

void moveSmallestToFront(struct Node **head) {
    if (*head == NULL || (*head)->next == NULL)
        return;

    struct Node *minPrev = NULL, *minNode = *head;
    struct Node *prev = NULL, *current = *head;

    while (current != NULL) {
        if (current->data < minNode->data) {
            minNode = current;
            minPrev = prev;
        }
        prev = current;
        current = current->next;
    }

    if (minPrev == NULL)
        return;  // Already at beginning

    minPrev->next = minNode->next;
    minNode->next = *head;
    *head = minNode;
}

void printList(struct Node *head) {
    struct Node *current = head;
    while (current != NULL) {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL, *temp = NULL;
    int n, data;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf("%d", &data);
        struct Node *newNode = createNode(data);
        if (head == NULL) {
            head = newNode;
            temp = head;
        } else {
            temp->next = newNode;
            temp = temp->next;
        }
    }

    printf("Original list: ");
    printList(head);

    moveSmallestToFront(&head);

    printf("List after moving smallest element to front: ");
    printList(head);

    return 0;
}

OUTPUT:
Enter the number of nodes: 5
Enter data for node 1: 10
Enter data for node 2: 50
Enter data for node 3: 5
Enter data for node 4: 20
Enter data for node 5: 40
Original list: 10 -> 50 -> 5 -> 20 -> 40 -> NULL
List after moving smallest element to front: 5 -> 10 -> 50 -> 20 -> 40 -> NULL
