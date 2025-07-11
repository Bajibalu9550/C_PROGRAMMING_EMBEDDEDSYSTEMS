# One-Dimensional Array in C

## What is a One-Dimensional Array?
A one-dimensional array is a linear collection of elements that are stored in contiguous memory locations and accessed by a single index.

## Syntax of One-Dimensional Array

```c
data_type array_name[size];
```

```c
int a[5];
float b[10];
char name[20];
```

## Memory Representation

```c
int a[5] = {10, 20, 30, 40, 50};
```

| Index | Value |
|-------|--------|
| a[0]  | 10     |
| a[1]  | 20     |
| a[2]  | 30     |
| a[3]  | 40     |
| a[4]  | 50     |

## Initialization of One-D Arrays

```c
int a[5] = {1, 2, 3, 4, 5};
int a[5] = {1, 2};
int a[] = {10, 20, 30};
```

## Accessing and Modifying Elements

```c
a[0] = 100;
printf("%d", a[0]);
```

```c
for (int i = 0; i < 5; i++) {
    printf("%d ", a[i]);
}
```

## Taking Input from User

```c
int a[5];
for (int i = 0; i < 5; i++) {
    scanf("%d", &a[i]);
}
```

## Displaying Array Elements

```c
for (int i = 0; i < 5; i++) {
    printf("%d ", a[i]);
}
```

## Example Program – Sum of Array Elements

```c
#include <stdio.h>

int main() {
    int a[5] = {10, 20, 30, 40, 50};
    int sum = 0;

    for (int i = 0; i < 5; i++) {
        sum += a[i];
    }

    printf("Sum = %d\n", sum);
    return 0;
}
```

## Common Operations on 1D Arrays

| Operation     | Description               |
|---------------|---------------------------|
| Traversal     | Visit all elements        |
| Insertion     | Insert value at index     |
| Deletion      | Remove element at index   |
| Searching     | Linear or binary search   |
| Sorting       | Bubble, selection sort    |

## Advantages

- Easy to declare and use
- Fast access using index (O(1))
- Contiguous memory improves cache performance

## Limitations

- Fixed size
- Wastes memory if partially filled
- No bounds checking

## Real-Life Use Cases

- Store marks of students
- List of prices
- Daily temperature readings
- Character array used for strings

