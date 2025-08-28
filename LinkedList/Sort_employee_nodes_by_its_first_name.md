# C Program to Sort Employee Nodes by First Name in a Linked List

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

struct Employee* sortByName(struct Employee *head) {
    if (head == NULL) return NULL;
    struct Employee *i, *j;
    for (i = head; i != NULL; i = i->next) {
        for (j = i->next; j != NULL; j = j->next) {
            if (strcmp(i->name, j->name) > 0) {
                int tempId = i->id;
                float tempSalary = i->salary;
                char tempName[50];
                strcpy(tempName, i->name);

                i->id = j->id;
                i->salary = j->salary;
                strcpy(i->name, j->name);

                j->id = tempId;
                j->salary = tempSalary;
                strcpy(j->name, tempName);
            }
        }
    }
    return head;
}

int main() {
    struct Employee *head = NULL;
    head = insertEmployeeEnd(head, 103, "Aarav", 48000);
    head = insertEmployeeEnd(head, 101, "Devanshi", 50000);
    head = insertEmployeeEnd(head, 102, "Balu", 45000);

    printf("Original Employee List:\n");
    displayEmployees(head);

    head = sortByName(head);
    printf("\nEmployee List After Sorting by Name:\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Original Employee List:
ID: 103, Name: Aarav, Salary: 48000.00
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 102, Name: Balu, Salary: 45000.00

Employee List After Sorting by Name:
ID: 103, Name: Aarav, Salary: 48000.00
ID: 102, Name: Balu, Salary: 45000.00
ID: 101, Name: Devanshi, Salary: 50000.00
