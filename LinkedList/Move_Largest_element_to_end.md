# C Program to Move the Largest Element to the End of a Single Linked List

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

void moveLargestToEnd(struct Node **head) {
    if (*head == NULL || (*head)->next == NULL)
        return;

    struct Node *maxPrev = NULL, *maxNode = *head;
    struct Node *prev = NULL, *current = *head;

    while (current != NULL) {
        if (current->data > maxNode->data) {
            maxNode = current;
            maxPrev = prev;
        }
        prev = current;
        current = current->next;
    }

    if (maxNode->next == NULL)
        return;  // Already at end

    if (maxPrev != NULL)
        maxPrev->next = maxNode->next;
    else
        *head = maxNode->next;

    prev->next = maxNode;
    maxNode->next = NULL;
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

    moveLargestToEnd(&head);

    printf("List after moving largest element to end: ");
    printList(head);

    return 0;
}

OUTPUT:
Enter the number of nodes: 5
Enter data for node 1: 10
Enter data for node 2: 50
Enter data for node 3: 30
Enter data for node 4: 20
Enter data for node 5: 40
Original list: 10 -> 50 -> 30 -> 20 -> 40 -> NULL
List after moving largest element to end: 10 -> 30 -> 20 -> 40 -> 50 -> NULL
