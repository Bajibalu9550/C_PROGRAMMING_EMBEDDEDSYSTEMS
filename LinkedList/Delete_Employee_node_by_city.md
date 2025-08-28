# C Program to Delete an Employee Node by City in a Linked List

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Employee {
    int id;
    char name[50];
    char city[30];
    float salary;
    struct Employee *next;
};

struct Employee* createEmployee(int id, char name[], char city[], float salary) {
    struct Employee *newEmp = (struct Employee*)malloc(sizeof(struct Employee));
    newEmp->id = id;
    strcpy(newEmp->name, name);
    strcpy(newEmp->city, city);
    newEmp->salary = salary;
    newEmp->next = NULL;
    return newEmp;
}

struct Employee* insertEmployeeEnd(struct Employee *head, int id, char name[], char city[], float salary) {
    struct Employee *newEmp = createEmployee(id, name, city, salary);
    if (head == NULL)
        return newEmp;
    struct Employee *temp = head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newEmp;
    return head;
}

struct Employee* deleteByCity(struct Employee *head, char city[]) {
    struct Employee *temp = head, *prev = NULL;
    while (temp != NULL) {
        if (strcmp(temp->city, city) == 0) {
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
    printf("Employee with city '%s' not found.\n", city);
    return head;
}

void displayEmployees(struct Employee *head) {
    struct Employee *temp = head;
    while (temp != NULL) {
        printf("ID: %d, Name: %s, City: %s, Salary: %.2f\n", temp->id, temp->name, temp->city, temp->salary);
        temp = temp->next;
    }
}

int main() {
    struct Employee *head = NULL;
    head = insertEmployeeEnd(head, 101, "Devanshi Sharma", "Bangalore", 50000);
    head = insertEmployeeEnd(head, 102, "Balu Mehta", "Mumbai", 45000);
    head = insertEmployeeEnd(head, 103, "Aarav Singh", "Delhi", 48000);

    printf("Original Employee List:\n");
    displayEmployees(head);

    char city[30];
    printf("\nEnter the city of the employee to delete: ");
    scanf("%s", city);

    head = deleteByCity(head, city);
    printf("\nEmployee List After Deletion:\n");
    displayEmployees(head);

    return 0;
}

OUTPUT:
Original Employee List:
ID: 101, Name: Devanshi Sharma, City: Bangalore, Salary: 50000.00
ID: 102, Name: Balu Mehta, City: Mumbai, Salary: 45000.00
ID: 103, Name: Aarav Singh, City: Delhi, Salary: 48000.00

Enter the city of the employee to delete: Mumbai

Employee List After Deletion:
ID: 101, Name: Devanshi Sharma, City: Bangalore, Salary: 50000.00
ID: 103, Name: Aarav Singh, City: Delhi, Salary: 48000.00
