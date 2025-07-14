# Program: Pointer to Array of Pointers to Structures in C

This program demonstrates how to use an **array of pointers to structures**, dynamically allocating memory for each structure and accessing its members using the `->` operator.

---

## Source Code

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct person {
    char name[20];
    int age;
} Node;

int main() {
    Node *a[3];  

    for (int i = 0; i < 3; i++) {
        a[i] = malloc(sizeof(Node));
        if (a[i] == NULL) {
            printf("Memory allocation failed.");
            return 1;
        }
        printf("Enter name of person %d: ", i + 1);
        scanf("%s", a[i]->name);

        printf("Enter age of %d Person: ", i + 1);
        scanf("%d", &a[i]->age);
    }

    printf("\n\n");

    for (int i = 0; i < 3; i++) {
        printf("Name of %d Person: %s\n", i + 1, a[i]->name);
        printf("Age of %d Person: %d\n", i + 1, a[i]->age);
        free(a[i]);
    }
    return 0;
}


**Sample Input/Output**
Input:

Enter name of person 1: Pagolu Bajibalu
Enter age of 1 Person: 22
Enter name of person 2: Yemineni Naga Venkat
Enter age of 2 Person: 28
Enter name of person 3: Dantu Venkata Pavan
Enter age of 3 Person: 25

Output:

Name of 1 Person: Pagolu Bajibalu
Age of 1 Person: 22
Name of 2 Person: Yemineni Naga Venkat
Age of 2 Person: 28
Name of 3 Person: Dantu Venkata Pavan
Age of 3 Person: 25
