1. Write a Program to print the address of variables using the address operator.
```
#include <stdio.h>
int main() {
    int a = 10;
    float b = 20.5;
    char c = 'X';

    printf("Address of a: %p\n", (void*)&a);
    printf("Address of b: %p\n", (void*)&b);
    printf("Address of c: %p\n", (void*)&c);

    return 0;
}
```
2. Write a program to print size of pointer variables.
```
#include <stdio.h>
int main() {
    int *p1;
    float *p2;
    char *p3;
    double *p4;

    printf("Size of int pointer: %zu\n", sizeof(p1));
    printf("Size of float pointer: %zu\n", sizeof(p2));
    printf("Size of char pointer: %zu\n", sizeof(p3));
    printf("Size of double pointer: %zu\n", sizeof(p4));

    return 0;
}
```
3. Write a program to print size of pointer variables and size of values Dereferenced by them.
```
#include <stdio.h>
int main() {
    int *p1, x = 5;
    float *p2, y = 10.5;
    char *p3, z = 'A';

    p1 = &x;
    p2 = &y;
    p3 = &z;

    printf("Size of int pointer: %zu, Size of value: %zu\n", sizeof(p1), sizeof(*p1));
    printf("Size of float pointer: %zu, Size of value: %zu\n", sizeof(p2), sizeof(*p2));
    printf("Size of char pointer: %zu, Size of value: %zu\n", sizeof(p3), sizeof(*p3));

    return 0;
}
```
4. Write a program to illustrate the dereferencing of pointers.
```
#include <stdio.h>
int main() {
    int a = 100;
    int *p = &a;

    printf("Value of a: %d\n", a);
    printf("Value using pointer: %d\n", *p);

    *p = 200; // changing value using pointer
    printf("New value of a: %d\n", a);

    return 0;
}
```
5. C program to illustrate pointer arithmetic
```
#include <stdio.h>
int main() {
    int arr[3] = {10, 20, 30};
    int *p = arr;

    printf("p points to: %d\n", *p);
    p++;
    printf("After p++, p points to: %d\n", *p);
    p--;
    printf("After p--, p points to: %d\n", *p);

    return 0;
}
```
6. Write a program to declare an integer variable a, assign it a value, then declare a pointer variable, assign it the address of a, and finally print the value of a using the pointer variable.
```
#include <stdio.h>
int main() {
    int a = 50;
    int *p = &a;

    printf("Value of a: %d\n", *p);

    return 0;
}
```
7. Write a program to print postfix/prefix increment/decrement in a pointer variable of base type int*.
```
#include <stdio.h>
int main() {
    int arr[3] = {11, 22, 33};
    int *p = arr;

    printf("Original: %d\n", *p);
    printf("Postfix p++: %d\n", *p++);
    printf("Now *p: %d\n", *p);
    printf("Prefix ++p: %d\n", *(++p));
    printf("Prefix --p: %d\n", *(--p));

    return 0;
}
```
8. Write a Program to print the value and address of elements of an array using pointers notation.
```
#include <stdio.h>
int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int *p = arr;

    for (int i = 0; i < 5; i++) {
        printf("Value: %d, Address: %p\n", *(p+i), (void*)(p+i));
    }
    return 0;
}
```
9. Write a program to print the value of array elements using pointers and subscript notation.
```
#include <stdio.h>
int main() {
    int arr[4] = {5, 15, 25, 35};
    int *p = arr;

    printf("Using pointer arithmetic: %d %d %d %d\n", *(p), *(p+1), *(p+2), *(p+3));
    printf("Using subscript notation: %d %d %d %d\n", p[0], p[1], p[2], p[3]);

    return 0;
}
```
10. Write a program to print the value and address of array elements by subscripting a pointer variable.
```
#include <stdio.h>
int main() {
    int arr[3] = {2, 4, 6};
    int *p = arr;

    for (int i = 0; i < 3; i++) {
        printf("arr[%d] = %d, Address = %p\n", i, p[i], (void*)&p[i]);
    }

    return 0;
}
```
11. Program to understand the difference between a pointer to an integer and a pointer to an array of integers.
```
#include <stdio.h>
int main() {
    int a = 10;
    int *p1 = &a;      // pointer to integer
    int arr[3] = {1,2,3};
    int (*p2)[3] = &arr; // pointer to array of 3 integers

    printf("Pointer to int: %d\n", *p1);
    printf("Pointer to array first element: %d\n", (*p2)[0]);

    return 0;
}
```
12. Write a program to dereference a pointer to an array.
```
#include <stdio.h>
int main() {
    int arr[4] = {10, 20, 30, 40};
    int (*p)[4] = &arr;

    for (int i = 0; i < 4; i++) {
        printf("%d ", (*p)[i]);
    }
    return 0;
}
```
13. Program to print the values and addresses of elements of a 2-D array.
```
#include <stdio.h>
int main() {
    int arr[2][3] = {{1,2,3}, {4,5,6}};

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("Value: %d, Address: %p\n", arr[i][j], (void*)&arr[i][j]);
        }
    }
    return 0;
}
```
14. Program to print elements of a 2-D array by subscripting a pointer to an array variable.
```
#include <stdio.h>
int main() {
    int arr[2][3] = {{10,20,30},{40,50,60}};
    int (*p)[3] = arr;

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", p[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
15. Program to print elements of a 3-D array using pointer notation.
```
#include <stdio.h>
int main() {
    int arr[2][2][2] = {{{1,2},{3,4}}, {{5,6},{7,8}}};
    int *p = &arr[0][0][0];

    for (int i = 0; i < 8; i++) {
        printf("%d ", *(p+i));
    }
    return 0;
}
```
16. Write a simple program for call by value.
```
#include <stdio.h>
void change(int x) {
    x = x + 10;
    printf("Inside function: %d\n", x);
}
int main() {
    int a = 5;
    change(a);
    printf("In main: %d\n", a);
    return 0;
}
```
17. Write a simple program for call by reference.
```
#include <stdio.h>
void change(int *x) {
    *x = *x + 10;
}
int main() {
    int a = 5;
    change(&a);
    printf("In main after call: %d\n", a);
    return 0;
}
```
18. Program to return more than one value from a function using call by reference.
```
#include <stdio.h>
void compute(int a, int b, int *sum, int *prod) {
    *sum = a + b;
    *prod = a * b;
}
int main() {
    int x = 3, y = 4, s, p;
    compute(x, y, &s, &p);
    printf("Sum: %d, Product: %d\n", s, p);
    return 0;
}
```
19. Write a program to pass a 1D array to a function.
```
#include <stdio.h>
`void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}
int main() {
    int arr[5] = {1,2,3,4,5};
    printArray(arr, 5);
    return 0;
}
```
20. Create a function that swaps two numbers using pointers.
```
#include <stdio.h>
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
int main() {
    int x = 10, y = 20;
    swap(&x, &y);
    printf("x = %d, y = %d\n", x, y);
    return 0;
}
```
21. Implement a function that returns the length of a string using pointers.
```
#include <stdio.h>
int strLength(char *s) {
    int len = 0;
    while (*s != '\0') {
        len++;
        s++;
    }
    return len;
}
int main() {
    char str[] = "PointerDemo";
    printf("Length: %d\n", strLength(str));
    return 0;
}
```
22. Write a program to find the maximum and minimum elements in an array using pointers.
```
#include <stdio.h>
int main() {
    int arr[5] = {22, 5, 11, 89, 43};
    int *p = arr;
    int max = *p, min = *p;

    for (int i = 1; i < 5; i++) {
        if (*(p+i) > max) max = *(p+i);
        if (*(p+i) < min) min = *(p+i);
    }
    printf("Max = %d, Min = %d\n", max, min);
    return 0;
}
```
23. Develop a function to reverse a string in place using pointers.
```
#include <stdio.h>
#include <string.h>
void reverse(char *s) {
    char *start = s;
    char *end = s + strlen(s) - 1;
    char temp;
    while (start < end) {
        temp = *start;
        *start = *end;
        *end = temp;
        start++;
        end--;
    }
}
int main() {
    char str[] = "Pointers";
    reverse(str);
    printf("Reversed: %s\n", str);
    return 0;
}
```
