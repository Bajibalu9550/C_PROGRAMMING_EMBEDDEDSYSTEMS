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
24. Calculate the sum of all elements in an integer array using pointer arithmetic.
```
#include <stdio.h>
int main() {
    int arr[5] = {1,2,3,4,5};
    int *p = arr;
    int sum = 0;
    for (int i = 0; i < 5; i++)
        sum += *(p + i);
    printf("Sum = %d\n", sum);
    return 0;
}
```
25. Copy one string into another using pointers (without library functions).
```
#include <stdio.h>
void strCopy(char *dest, char *src) {
    while (*src) {
        *dest = *src;
        dest++;
        src++;
    }
    *dest = '\0';
}
int main() {
    char str1[] = "Hello";
    char str2[10];
    strCopy(str2, str1);
    printf("Copied String: %s\n", str2);
    return 0;
}
```
26. Compare two strings lexicographically using pointers.
```
#include <stdio.h>
int strCompare(char *s1, char *s2) {
    while (*s1 && (*s1 == *s2)) {
        s1++;
        s2++;
    }
    return *s1 - *s2;
}
int main() {
    char a[] = "Apple", b[] = "Apples";
    int res = strCompare(a, b);
    printf("Comparison Result: %d\n", res);
    return 0;
}
```
27. Reverse an array of integers in place using pointers.
```
#include <stdio.h>
void reverseArray(int *arr, int n) {
    int *start = arr, *end = arr + n - 1, temp;
    while (start < end) {
        temp = *start;
        *start = *end;
        *end = temp;
        start++;
        end--;
    }
}
int main() {
    int arr[] = {1,2,3,4,5};
    reverseArray(arr, 5);
    for (int i = 0; i < 5; i++) printf("%d ", arr[i]);
    return 0;
}
```
28. Find the largest element using Dynamic Memory Allocation.
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int n;
    printf("Enter size: "); scanf("%d",&n);
    int *arr = (int*)malloc(n * sizeof(int));
    for (int i = 0; i < n; i++) scanf("%d", arr + i);
    int max = *arr;
    for (int i = 1; i < n; i++) if (*(arr + i) > max) max = *(arr + i);
    printf("Max = %d\n", max);
    free(arr);
    return 0;
}
```
29. Calculate the length of a string using a pointer.
```
#include <stdio.h>
int main() {
    char str[] = "Pointers";
    char *p = str;
    int len = 0;
    while (*p++) len++;
    printf("Length = %d\n", len);
    return 0;
}
```
30. Swap elements using call by reference.
```
#include <stdio.h>
void swap(int *a, int *b) {
    int t = *a;
    *a = *b;
    *b = t;
}
int main() {
    int x=5, y=10;
    swap(&x,&y);
    printf("x=%d y=%d\n", x, y);
    return 0;
}
```
31. Factorial of a number using pointers.
```
#include <stdio.h>
int factorial(int *n) {
    int fact = 1;
    for (int i = 1; i <= *n; i++) fact *= i;
    return fact;
}
int main() {
    int num = 5;
    printf("Factorial = %d\n", factorial(&num));
    return 0;
}
```
32. Count vowels and consonants in a string using a pointer.
```
#include <stdio.h>
int main() {
    char str[] = "HelloWorld";
    char *p = str;
    int vowels=0, consonants=0;
    while (*p) {
        if (*p=='a'||*p=='e'||*p=='i'||*p=='o'||*p=='u'||
            *p=='A'||*p=='E'||*p=='I'||*p=='O'||*p=='U')
            vowels++;
        else if ((*p>='a' && *p<='z') || (*p>='A' && *p<='Z'))
            consonants++;
        p++;
    }
    printf("Vowels=%d, Consonants=%d\n", vowels, consonants);
    return 0;
}
```
33. Sort an array using a pointer.
```
#include <stdio.h>
int main() {
    int arr[] = {5,2,9,1,6};
    int *p = arr, temp;
    for (int i = 0; i < 5-1; i++)
        for (int j = i+1; j < 5; j++)
            if (*(p+i) > *(p+j)) {
                temp = *(p+i);
                *(p+i) = *(p+j);
                *(p+j) = temp;
            }
    for (int i=0;i<5;i++) printf("%d ", *(p+i));
    return 0;
}
```
34. Demonstrate how a function returns a pointer.
```
#include <stdio.h>
int* getMax(int *a, int *b) {
    return (*a > *b) ? a : b;
}
int main() {
    int x=5, y=10;
    int *max = getMax(&x,&y);
    printf("Max = %d\n", *max);
    return 0;
}
```
35. Compute the sum of all elements in an array using pointers.
```
#include <stdio.h>
int main() {
    int arr[] = {1,2,3,4,5};
    int *p = arr, sum = 0;
    for (int i=0;i<5;i++) sum += *(p+i);
    printf("Sum = %d\n", sum);
    return 0;
}
```
36. Print elements of an array in reverse order using pointers.
```
#include <stdio.h>
int main() {
    int arr[] = {1,2,3,4,5};
    int *p = arr + 4;
    for (int i=0;i<5;i++) printf("%d ", *(p-i));
    return 0;
}
```
37. Pointer to an array whose contents are pointers to structures.
```
#include <stdio.h>
struct Point { int x, y; };
int main() {
    struct Point a={1,2}, b={3,4};
    struct Point *arr[2] = {&a, &b};
    struct Point **p = arr;
    for (int i=0;i<2;i++)
        printf("x=%d y=%d\n", (*p+i)->x, (*p+i)->y);
    return 0;
}


```

39. Logic to search an element in an array using pointers.
```
#include <stdio.h>
int main() {
    int arr[] = {1,3,5,7,9};
    int *p = arr;
    int key = 5, found=0;
    for (int i=0;i<5;i++)
        if (*(p+i) == key) { found=1; break; }
    printf(found ? "Found\n" : "Not Found\n");
    return 0;
}
```
40. Add two matrices using pointers.
```
#include <stdio.h>
int main() {
    int a[2][2]={{1,2},{3,4}}, b[2][2]={{5,6},{7,8}}, sum[2][2];
    int (*pa)[2]=a, (*pb)[2]=b, (*ps)[2]=sum;
    for(int i=0;i<2;i++)
        for(int j=0;j<2;j++)
            ps[i][j] = pa[i][j] + pb[i][j];
    for(int i=0;i<2;i++) {
        for(int j=0;j<2;j++) printf("%d ", ps[i][j]);
        printf("\n");
    }
    return 0;
}
```
41. Multiply two matrices using pointers.
```
#include <stdio.h>
int main() {
    int a[2][2]={{1,2},{3,4}}, b[2][2]={{2,0},{1,2}}, c[2][2]={0};
    int (*pa)[2]=a, (*pb)[2]=b;
    for(int i=0;i<2;i++)
        for(int j=0;j<2;j++)
            for(int k=0;k<2;k++)
                c[i][j] += pa[i][k] * pb[k][j];
    for(int i=0;i<2;i++) {
        for(int j=0;j<2;j++) printf("%d ", c[i][j]);
        printf("\n");
    }
    return 0;
}
```
42. Concatenate two strings using pointers.
```
#include <stdio.h>
int main() {
    char str1[20] = "Hello ";
    char str2[] = "World";
    char *p = str1;
    while (*p) p++; // move to end of str1
    char *q = str2;
    while (*q) {
        *p = *q;
        p++; q++;
    }
    *p = '\0';
    printf("Concatenated String: %s\n", str1);
    return 0;
}
```

43. Input elements in an array and sort array using pointers.
```
#include <stdio.h>
int main() {
    int n=5, arr[5], *p=arr, temp;
    printf("Enter 5 elements: ");
    for(int i=0;i<n;i++) scanf("%d", p+i);
    for(int i=0;i<n-1;i++)
        for(int j=i+1;j<n;j++)
            if (*(p+i) > *(p+j)) {
                temp = *(p+i);
                *(p+i) = *(p+j);
                *(p+j) = temp;
            }
    printf("Sorted Array: ");
    for(int i=0;i<n;i++) printf("%d ", *(p+i));
    return 0;
}
```
44. Access dynamically allocated memory as a 1D array.
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int n = 5;
    int *arr = (int*)malloc(n * sizeof(int));
    for(int i=0;i<n;i++) arr[i] = i+1;
    for(int i=0;i<n;i++) printf("%d ", arr[i]);
    free(arr);
    return 0;
}
```
45. Access dynamically allocated 2-D array using a pointer to an array.
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int rows=2, cols=3;
    int (*arr)[3] = malloc(rows * sizeof *arr);
    int val = 1;
    for(int i=0;i<rows;i++)
        for(int j=0;j<cols;j++)
            arr[i][j] = val++;
    for(int i=0;i<rows;i++) {
        for(int j=0;j<cols;j++) printf("%d ", arr[i][j]);
        printf("\n");
    }
    free(arr);
    return 0;
}
```
46. Print array of pointers.
```
#include <stdio.h>
int main() {
    int a=10, b=20, c=30;
    int *arr[3] = {&a, &b, &c};
    for(int i=0;i<3;i++) printf("%d ", *arr[i]);
    return 0;
}

47. Print pointer to an array.
#include <stdio.h>
int main() {
    int arr[3] = {1,2,3};
    int (*p)[3] = &arr;
    for(int i=0;i<3;i++) printf("%d ", (*p)[i]);
    return 0;
}
```
48. Dynamically allocate a 2-D array using array of pointers.
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int rows=2, cols=3;
    int **arr = malloc(rows * sizeof(int*));
    for(int i=0;i<rows;i++)
        arr[i] = malloc(cols * sizeof(int));
    int val=1;
    for(int i=0;i<rows;i++)
        for(int j=0;j<cols;j++)
            arr[i][j]=val++;
    for(int i=0;i<rows;i++) {
        for(int j=0;j<cols;j++) printf("%d ", arr[i][j]);
        printf("\n");
    }
    for(int i=0;i<rows;i++) free(arr[i]);
    free(arr);
    return 0;
}
```
49. Invoke a function using function pointer.
```
#include <stdio.h>
int add(int a, int b) { return a+b; }
int main() {
    int (*fp)(int,int) = add;
    int result = fp(5,10);
    printf("Result = %d\n", result);
    return 0;
}
```
50. Program to send a function’s address as an argument to another function

```
#include <stdio.h>

void greet() {
    printf("Hello from greet function!\n");
}

void callFunction(void (*func)()) {
    func();  
}

int main() {
    callFunction(greet);  
    return 0;
}
```
51. Program to pass a pointer containing function's arguments address as an argument
```
#include <stdio.h>

void add(int *a, int *b) {
    printf("Sum = %d\n", *a + *b);
}

void execute(void (*func)(int*, int*), int *x, int *y) {
    func(x, y);
}

int main() {
    int num1 = 10, num2 = 20;
    execute(add, &num1, &num2);  
    return 0;
}
```
52. Program using call by reference (pointer)
```
#include <stdio.h>

void fun(int *ptr) {
    *ptr = 30;  
}

int main() {
    int y = 20;
    fun(&y);  
    printf("%d", y);
    return 0;
}


Output:

30
```

53. Program using call by value
```
#include <stdio.h>

void fun(int x) {
    x = 30;  
}

int main() {
    int y = 20;
    fun(y);
    printf("%d", y);
    return 0;
}


Output:

20
````
54. Program using pointers (call by reference)
```
#include <stdio.h>

void fun(int *ptr) {
    *ptr = 30;  
}

int main() {
    int y = 20;
    fun(&y);  
    printf("%d", y);
    return 0;
}


Output:

30


```
55. Program using pointers to modify value
```
#include <stdio.h>

void changeValue(int *ptr) {
    *ptr = 30; 
}

int main() {
    int val = 20;
    int *ptr = &val;  
    changeValue(ptr); 
    printf("%d", val);
}


Output:

30
```
56. Output of calloc program
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int *arr = (int *)calloc(5, sizeof(int));
    for (int i = 0; i < 5; i++) {
        *(arr + i) = i;
    }
    printf("%d", arr[3]);
    free(arr);
}


Output:

3


```

57. Pointer assignment inside function
```
#include<stdio.h>
void f(int *p, int *q) {
    p = q;
    *p = 2;
}
int main() {
    int i = 0, j = 1;
    f(&i, &j);
    printf("%d %d", i, j);
    return 0;
}


Output:

0 2


```

58. Void pointer dereference (invalid)
```
int main() {
    int a = 12;
    void *ptr = (int *)&a;
    printf("%d", *ptr); // Invalid: cannot dereference void pointer
    return 0;
}


Output:
Compilation error.
```
59. Unary and post-decrement
```
int main() {
    int a, b = 10;
    a = -b--;
    printf("a = %d, b = %d", a, b);
    return 0;
}


Output:

a = -10, b = 9
```
60. Array comparison
```
int main() {
    int array[5][5];
    printf("%d", ((array == *array) && (*array == array[0])));
    return 0;
}


Output:

1


```
61. Double pointer
```
#include<stdio.h>
int main() {
    int x = 10;
    int *y, **z;
    y = &x;
    z = &y;
    printf("x = %d, y = %d, z = %d\n", x, *y, **z);
    return 0;
}


Output:

x = 10, y = 10, z = 10
```
62. Char arithmetic
```
#include <stdio.h>
int main() {
    char a = 30, b = 40, c = 10;
    char d = (a * b) / c;
    printf("%d", d);
    return 0;
}


Output:

120
```
63. Empty array size
```
#include <stdio.h>
int main() {
    int arr[] = {};
    printf("%d", sizeof(arr));
    return 0;
}


Output:

0
```
64. 2D array pointer notation
```
#include<stdio.h>
int main() {
    int a[2][3] = {2,1,3,2,3,4};
    printf("%d %d %d\n", *(*(a+0)+0), *(*(a+0)+1), *(*(a+0)+2));
    printf("%d %d %d\n", *(a[1]+0), *(a[1]+1), *(a[1]+2));
    return 0;
}


Output:

2 1 3
2 3 4
```
65. Pointer increment type mismatch
```
int a = 10, *j;
void *k;
j = k = &a;
j++;
k++;


Output:
Compilation error.
```
66. Pointer arithmetic
```
int arr[] = {10, 20, 30, 40, 50};
int *ptr1 = arr;
int *ptr2 = arr + 3;
printf("%d", (ptr2 - ptr1));


Output:

3
```
67. Pointer increment
```
int x = 5;
int *p = &x;
*p = *p + 1;
printf("%d", x);


Output:

6
```
68. Swap using pointers
```
int a = 10, b = 20;
int *p1 = &a, *p2 = &b;
*p1 += *p2;
*p2 = *p1 - *p2;
*p1 = *p1 - *p2;
printf("a=%d, b=%d", a, b);


Output:

a=20, b=10
```
69. String pointer
```
char *str = "hello";
printf("%c", *(str+1));


Output:

e
```
70. Update via pointer
```
void update(int *p) {
    *p += 5;
}
int main() {
    int a = 5;
    update(&a);
    printf("%d", a);
}


Output:

10
```
71. Pointer increment
```
int arr[] = {1, 2, 3, 4, 5};
int *p = arr;
++*p;
printf("%d", *p);


Output:

2
```
72. Modify string literal
```
char *s = "hello world";
s[0] = 'H'; 


Output:
Segmentation fault (runtime error).
```
73. Use after free
```
int *p = (int *)malloc(sizeof(int));
*p = 10;
free(p);
*p = 20;
printf("%d", *p);


Output:
Undefined behavior (may print garbage or crash).
```
74. Return address of local variable
```
int func() {
    int num = 10;
    return &num; // Invalid
}


Output:
Compilation error / undefined behavior.
```
75. Pointer arithmetic in array
```
int nums[] = {1,2,3,4,5};
int *ptr = nums + 2;
printf("%d", *(ptr + 1));


Output:

4
```
76. Swap via pointers
```
void swap(int *x, int *y) {
    int temp = *x; *x = *y; *y = temp;
}
int main() {
    int a = 10, b = 20;
    swap(&a, &b);
    printf("a=%d, b=%d", a, b);
}


Output:

a=20, b=10
```
77. Pointer increment
```
int arr[3] = {0,1,2};
int *ptr = arr;
printf("%d ", *++ptr);
printf("%d", *ptr++);


Output:

1 1
```
78. Triple pointer
```
int x = 10;
int *p = &x;
int **q = &p;
int ***r = &q;
***r = 20;
printf("%d", x);


Output:

20
```
79. Pointer subtraction
```
int arr[] = {10,20,30,40,50};
int *ptr1 = arr;
int *ptr2 = ptr1 + 3;
printf("%td", ptr2 - ptr1);


Output:

3
```
80. Array squares
```
void foo(int *array, int size) {
    for (int i = 0; i < size; i++) {
        *(array + i) = i * i;
    }
}
int main() {
    int arr[5];
    foo(arr, 5);
    printf("%d", arr[3]);
}


Output:

9
```
81. String pointer
```
char str[] = "pointer";
char *p = str;
p += 3;
printf("%s", p);


Output:

nter
```
82. Array pointer arithmetic
```
int a[3] = {1,2,3};
int *b = a;
*b += 2;
*(b+1) += 2;
b[2] += 2;
printf("%d %d %d", a[0], a[1], a[2]);


Output:

3 4 5
```
83. Pointer to pointer
```
void increase(int **p) {
    int q = 10;
    *p = &q;
}
int main() {
    int r = 20;
    int *ptr = &r;
    increase(&ptr);
    printf("%d", *ptr);
}


Output:
Undefined behavior (pointer points to local variable q).
```
84. realloc example
```
int *p = (int *)malloc(2*sizeof(int));
p[0]=1; p[1]=2;
realloc(p,4*sizeof(int));
p[2]=3; p[3]=4;
printf("%d %d %d %d", p[0], p[1], p[2], p[3]);


Output:
Undefined behavior (result of realloc not assigned back to p).
```
85. Pointer to pointer to pointer strings
```
char *s[] = {"knowledge","is","power"};
char **ptr[] = {s+2,s+1,s};
char ***pptr = ptr;
printf("%s ", **++pptr);
printf("%s ", *--*++pptr+3);
printf("%s", **pptr+1);


Output:

is erower
```
86. Pointer subtraction
```
int nums[] = {1,2,3,4};
int *p = nums + 3;
printf("%d", *(p-2));


Output:

2
```
87. Pointer manipulation
```
int *ptr;
int x;
ptr = &x;
*ptr = 0;
printf(" x = %d\n", x);
printf(" *ptr = %d\n", *ptr);
*ptr += 5;
printf(" x  = %d\n", x);
printf(" *ptr = %d\n", *ptr);
(*ptr)++;
printf(" x = %d\n", x);
printf(" *ptr = %d\n", *ptr);


Output:

x = 0
*ptr = 0
x = 5
*ptr = 5
x = 6
*ptr = 6
```
