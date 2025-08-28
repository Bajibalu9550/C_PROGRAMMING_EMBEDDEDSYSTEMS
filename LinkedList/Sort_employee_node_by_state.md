# C Program to Sort Employee Nodes by State in a Linked List

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Employee {
    int id;
    char name[50];
    char state[30];
    float salary;
    struct Employee *next;
};

struct Employee* createEmployee(int id, char name[], char state[], float salary) {
    struct Employee *newEmp = (struct Employee*)malloc(sizeof(struct Employee));
    newEmp->id = id;
    strcpy(newEmp->name, name);
    strcpy(newEmp->state, state);
    newEmp->salary = salary;
    newEmp->next = NULL;
    return newEmp;
}

struct Employee* insertEmployeeEnd(struct Employee *head, int id, char name[], char state[], float salary) {
    struct Employee *newEmp = createEmployee(id, name, state, salary);
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
        printf("ID: %d, Name: %s, State: %s, Salary: %.2f\n", temp->id, temp->name, temp->state, temp->salary);
        temp = temp->next;
    }
}

struct Employee* sortByState(struct Employee *head) {
    if (head == NULL) return NULL;
    struct Employee *i, *j;
    for (i = head; i != NULL; i = i->next) {
        for (j = i->next; j != NULL; j = j->next) {
            if (strcmp(i->state, j->state) > 0) {
                int tempId = i->id;
                float tempSalary = i->salary;
                char tempName[50], tempState[30];
                strcpy(tempName, i->name);
                strcpy(tempState, i->state);

                i->id = j->id;
                i->salary = j->salary;
                strcpy(i->name, j->name);
                strcpy(i->state, j->state);

                j->id = tempId;
                j->salary = tempSalary;
                strcpy(j->name, tempName);
                strcpy(j->state, tempState);
            }
        }
    }
    return head;
}

int main() {
    struct Employee *head = NULL;
    head = insertEmployeeEnd(head, 101, "Devanshi Sharma", "Karnataka", 50000);
    head = insertEmployeeEnd(head, 102, "Balu Mehta", "Maharashtra", 45000);
    head = insertEmployeeEnd(head, 103, "Aarav Singh", "Delhi", 48000);

    printf("Original Employee List:\n");
    displayEmployees(head);

    head = sortByState(head);
    printf("\nEmployee List After Sorting by State:\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Original Employee List:
ID: 101, Name: Devanshi Sharma, State: Karnataka, Salary: 50000.00
ID: 102, Name: Balu Mehta, State: Maharashtra, Salary: 45000.00
ID: 103, Name: Aarav Singh, State: Delhi, Salary: 48000.00

Employee List After Sorting by State:
ID: 103, Name: Aarav Singh, State: Delhi, Salary: 48000.00
ID: 101, Name: Devanshi Sharma, State: Karnataka, Salary: 50000.00
ID: 102, Name: Balu Mehta, State: Maharashtra, Salary: 45000.00
