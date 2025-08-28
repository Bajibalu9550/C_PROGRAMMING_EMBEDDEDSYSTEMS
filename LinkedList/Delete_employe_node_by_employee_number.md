# C Program to Delete an Employee Node by Employee Number in a Linked List

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

struct Employee* deleteByEmployeeNumber(struct Employee *head, int id) {
    struct Employee *temp = head, *prev = NULL;
    while (temp != NULL) {
        if (temp->id == id) {
            if (prev == NULL) {
                head = temp->next;
            } else {
                prev->next = temp->next;
            }
            free(temp);
            return head;
        }
        prev = temp;
        temp = temp->next;
    }
    printf("Employee with ID '%d' not found.\n", id);
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
    head = insertEmployeeEnd(head, 101, "Devanshi Sharma", 50000);
    head = insertEmployeeEnd(head, 102, "Balu Mehta", 45000);
    head = insertEmployeeEnd(head, 103, "Aarav Singh", 48000);

    printf("Original Employee List:\n");
    displayEmployees(head);

    int empId;
    printf("\nEnter the Employee ID to delete: ");
    scanf("%d", &empId);

    head = deleteByEmployeeNumber(head, empId);
    printf("\nEmployee List After Deletion:\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Original Employee List:
ID: 101, Name: Devanshi Sharma, Salary: 50000.00
ID: 102, Name: Balu Mehta, Salary: 45000.00
ID: 103, Name: Aarav Singh, Salary: 48000.00

Enter the Employee ID to delete: 102

Employee List After Deletion:
ID: 101, Name: Devanshi Sharma, Salary: 50000.00
ID: 103, Name: Aarav Singh, Salary: 48000.00
