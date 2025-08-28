# Delete an Employee Node at a Specific Position in the Linked List

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Employee {
    int id;
    char name[50];
    float salary;
    struct Employee *next;
};

struct Employee* deleteAtPosition(struct Employee *head, int pos) {
    if (head == NULL)
        return NULL;
    if (pos == 1) {
        struct Employee *temp = head;
        head = head->next;
        free(temp);
        return head;
    }
    struct Employee *temp = head;
    for (int i = 1; i < pos - 1 && temp != NULL; i++)
        temp = temp->next;

    if (temp == NULL || temp->next == NULL)
        return head;

    struct Employee *toDelete = temp->next;
    temp->next = temp->next->next;
    free(toDelete);
    return head;
}

struct Employee* createEmployee(int id, char name[], float salary) {
    struct Employee *newEmp = (struct Employee*)malloc(sizeof(struct Employee));
    newEmp->id = id;
    strcpy(newEmp->name, name);
    newEmp->salary = salary;
    newEmp->next = NULL;
    return newEmp;
}

struct Employee* insertEmployeeEnd(struct Employee *head, int id, char name[], float salary) {
    struct Employee *newEmp = createEmployee(id, name, salary);
    if (head == NULL)
        return newEmp;
    struct Employee *temp = head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newEmp;
    return head;
}

void displayEmployees(struct Employee *head) {
    struct Employee *temp = head;
    while (temp != NULL) {
        printf("ID: %d, Name: %s, Salary: %.2f\n", temp->id, temp->name, temp->salary);
        temp = temp->next;
    }
}

int main() {
    struct Employee *head = NULL;
    head = insertEmployeeEnd(head, 101, "Devanshi", 50000);
    head = insertEmployeeEnd(head, 102, "Balu", 45000);
    head = insertEmployeeEnd(head, 103, "Aarav", 48000);

    printf("Original List:\n");
    displayEmployees(head);

    int pos;
    printf("\nEnter the position to delete: ");
    scanf("%d", &pos);

    head = deleteAtPosition(head, pos);
    printf("\nList after deleting node at position %d:\n", pos);
    displayEmployees(head);

    return 0;
}

OUTPUT:
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 102, Name: Balu, Salary: 45000.00
ID: 103, Name: Aarav, Salary: 48000.00

Enter the position to delete: 2

List after deleting node at position 2:

List after deleting node at position %d:
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 103, Name: Aarav, Salary: 48000.00


