# Introduction to Arrays in C

## What is an Array?
An array is a collection of elements of the same data type stored contiguously in memory, and accessed using a single variable name with an index.

## Key Characteristics:
- Stores multiple values in a single variable.
- Each element is accessed using its index.
- Indexing starts from 0.
- All elements must be of the same data type.

## Why use Arrays?

```c
int a1, a2, a3, a4, a5;
```

```c
int a[5];
```

## Declaration of Arrays

```c
int marks[5];
float prices[10];
char name[20];
```

## Initialization of Arrays

```c
int a[5] = {10, 20, 30, 40, 50};
int a[5] = {10, 20};
int a[] = {1, 2, 3, 4};
```

## Accessing Elements

```c
a[0] = 5;
printf("%d", a[0]);
```

## Input and Output of Arrays

```c
int a[5];
for (int i = 0; i < 5; i++) {
    scanf("%d", &a[i]);
}
for (int i = 0; i < 5; i++) {
    printf("%d ", a[i]);
}
```

## Types of Arrays

```c
int a[5];
int mat[3][3];
int cube[2][3][4];
```

## Array Example: Find Maximum Element

```c
#include <stdio.h>

int main() {
    int a[5] = {10, 25, 7, 89, 15};
    int max = a[0];

    for (int i = 1; i < 5; i++) {
        if (a[i] > max)
            max = a[i];
    }

    printf("Maximum element is: %d\n", max);
    return 0;
}
```


