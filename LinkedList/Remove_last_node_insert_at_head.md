# C Program to Move the Last Node to the Beginning of a Single Linked List Without Changing Data

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

void moveLastToFront(struct Node **head) {
    if (*head == NULL || (*head)->next == NULL)
        return;

    struct Node *prev = NULL, *last = *head;
    while (last->next != NULL) {
        prev = last;
        last = last->next;
    }

    prev->next = NULL;
    last->next = *head;
    *head = last;
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

    moveLastToFront(&head);

    printf("List after moving last node to front: ");
    printList(head);

    return 0;
}

OUTPUT:
Enter the number of nodes: 5
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 30
Enter data for node 4: 40
Enter data for node 5: 50
Original list: 10 -> 20 -> 30 -> 40 -> 50 -> NULL
List after moving last node to front: 50 -> 10 -> 20 -> 30 -> 40 -> NULL
