# C Program to Create a Copy of a Single Linked List

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

struct Node* copyList(struct Node *head) {
    if (head == NULL)
        return NULL;

    struct Node *newHead = createNode(head->data);
    struct Node *currentOrig = head->next;
    struct Node *currentCopy = newHead;

    while (currentOrig != NULL) {
        currentCopy->next = createNode(currentOrig->data);
        currentCopy = currentCopy->next;
        currentOrig = currentOrig->next;
    }

    return newHead;
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

    struct Node *copy = copyList(head);
    printf("Copied list:   ");
    printList(copy);

    return 0;
}

OUTPUT:
Enter the number of nodes: 4
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 30
Enter data for node 4: 40
Original list: 10 -> 20 -> 30 -> 40 -> NULL
Copied list:   10 -> 20 -> 30 -> 40 -> NULL
