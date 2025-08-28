# C Program to Add an Employee Node at a Specific Position in a Linked List

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

// Function to create a new employee node
struct Employee* createEmployee(int id, char name[], float salary) {
    struct Employee *newEmp = (struct Employee*)malloc(sizeof(struct Employee));
    newEmp->id = id;
    strcpy(newEmp->name, name);
    newEmp->salary = salary;
    newEmp->next = NULL;
    return newEmp;
}

// Function to insert employee at a specific position (position starts from 1)
struct Employee* insertEmployeeAtPosition(struct Employee *head, int id, char name[], float salary, int pos) {
    struct Employee *newEmp = createEmployee(id, name, salary);

    if (pos == 1) {
        newEmp->next = head;
        return newEmp;
    }

    struct Employee *temp = head;
    for (int i = 1; i < pos - 1 && temp != NULL; i++)
        temp = temp->next;

    if (temp == NULL) {
        printf("Position exceeds list length. Inserting at end.\n");
        temp = head;
        while (temp->next != NULL)
            temp = temp->next;
        temp->next = newEmp;
    } else {
        newEmp->next = temp->next;
        temp->next = newEmp;
    }

    return head;
}

// Function to display all employees
void displayEmployees(struct Employee *head) {
    struct Employee *temp = head;
    while (temp != NULL) {
        printf("ID: %d, Name: %s, Salary: %.2f\n", temp->id, temp->name, temp->salary);
        temp = temp->next;
    }
}

int main() {
    struct Employee *head = NULL;
    int n, id, pos;
    char name[50];
    float salary;

    printf("Enter the number of employees: ");
    scanf("%d", &n);
    getchar();

    for (int i = 0; i < n; i++) {
        printf("Enter details of employee %d:\n", i + 1);
        printf("ID: ");
        scanf("%d", &id);
        getchar();
        printf("Name: ");
        fgets(name, sizeof(name), stdin);
        name[strcspn(name, "\n")] = '\0';
        printf("Salary: ");
        scanf("%f", &salary);
        getchar();

        printf("Enter position to insert employee %d: ", i + 1);
        scanf("%d", &pos);
        getchar();

        head = insertEmployeeAtPosition(head, id, name, salary, pos);
    }

    printf("\nEmployee List (after inserting at positions):\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Enter the number of employees: 3
Enter details of employee 1:
ID: 101
Name: Devanshi
Salary: 50000
Enter position to insert employee 1: 1
Enter details of employee 2:
ID: 102
Name: Balu
Salary: 45000
Enter position to insert employee 2: 2
Enter details of employee 3:
ID: 103
Name: Aarav
Salary: 48000
Enter position to insert employee 3: 2

Employee List (after inserting at positions):
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 103, Name: Aarav, Salary: 48000.00
ID: 102, Name: Balu, Salary: 45000.00
