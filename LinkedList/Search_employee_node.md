# C Program to Search an Employee Node in the Linked List

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

int searchEmployee(struct Employee *head, int id) {
    struct Employee *temp = head;
    int pos = 1;
    while (temp != NULL) {
        if (temp->id == id)
            return pos;
        temp = temp->next;
        pos++;
    }
    return 0; // Not found
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

    printf("Employee List:\n");
    displayEmployees(head);

    int searchId;
    printf("\nEnter the Employee ID to search: ");
    scanf("%d", &searchId);

    int position = searchEmployee(head, searchId);
    if (position)
        printf("Employee with ID %d found at position %d.\n", searchId, position);
    else
        printf("Employee with ID %d not found in the list.\n", searchId);

    return 0;
}

OUTPUT:
Employee List:
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 102, Name: Balu, Salary: 45000.00
ID: 103, Name: Aarav, Salary: 48000.00

Enter the Employee ID to search: 102
Employee with ID 102 found at position 2.

