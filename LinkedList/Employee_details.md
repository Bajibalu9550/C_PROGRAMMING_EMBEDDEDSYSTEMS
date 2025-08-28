# C Program to Create a Linked List to Store Employee Details

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

// Function to insert employee at the end of the list
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
    int n, id;
    char name[50];
    float salary;

    printf("Enter the number of employees: ");
    scanf("%d", &n);
    getchar(); // consume newline

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

        head = insertEmployeeEnd(head, id, name, salary);
    }

    printf("\nEmployee List:\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Enter the number of employees: 2
Enter details of employee 1:
ID: 101
Name: Devanshi
Salary: 50000
Enter details of employee 2:
ID: 102
Name: Balu
Salary: 45000

Employee List:
ID: 101, Name: Devanshi, Salary: 50000.00
ID: 102, Name: Balu, Salary: 45000.00
