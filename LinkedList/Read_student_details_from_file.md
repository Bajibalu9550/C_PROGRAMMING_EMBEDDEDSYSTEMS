# C Program to Read Student Data from a File and Store in an Array of Structures

```c
#include <stdio.h>
#include <stdlib.h>

struct Student {
    char name[50];
    int roll;
    float marks;
};

int main() {
    FILE *file = fopen("students.txt", "r");
    if (file == NULL) {
        printf("Unable to open file.\n");
        return 1;
    }

    struct Student students[100];
    int count = 0;

    while (fscanf(file, "%s %d %f", students[count].name, &students[count].roll, &students[count].marks) == 3) {
        count++;
    }

    fclose(file);

    printf("Student Data:\n");
    for (int i = 0; i < count; i++) {
        printf("Name: %s, Roll: %d, Marks: %.2f\n", students[i].name, students[i].roll, students[i].marks);
    }

    return 0;
}
```
