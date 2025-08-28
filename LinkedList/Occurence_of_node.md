# C Program to Count the Number of Occurrences of an Element in a Single Linked List (User Input Nodes)

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

int countOccurrences(struct Node *head, int key) {
    int count = 0;
    struct Node *current = head;
    while (current != NULL) {
        if (current->data == key)
            count++;
        current = current->next;
    }
    return count;
}

struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node *head = NULL, *temp = NULL;
    int n, data, key;

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

    printf("Enter the element to count: ");
    scanf("%d", &key);

    int count = countOccurrences(head, key);
    printf("Element %d occurs %d times in the linked list.\n", key, count);

    return 0;
}

OUTPUT:
Enter the number of nodes: 5
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 10
Enter data for node 4: 30
Enter data for node 5: 10
Enter the element to count: 10
Element 10 occurs 3 times in the linked list.
