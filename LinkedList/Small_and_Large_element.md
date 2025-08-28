# C Program to Find the Smallest and Largest Element in a Single Linked List

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void findMinMax(struct Node *head, int *min, int *max) {
    if (head == NULL) {
        *min = *max = 0;
        return;
    }

    *min = *max = head->data;
    struct Node *current = head->next;

    while (current != NULL) {
        if (current->data < *min)
            *min = current->data;
        if (current->data > *max)
            *max = current->data;
        current = current->next;
    }
}

struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node *head = NULL, *temp = NULL;
    int n, data, min, max;

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

    findMinMax(head, &min, &max);
    printf("Smallest element: %d\n", min);
    printf("Largest element: %d\n", max);

    return 0;
}

OUTPUT:
Enter the number of nodes: 5
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 5
Enter data for node 4: 30
Enter data for node 5: 15
Smallest element: 5
Largest element: 30
