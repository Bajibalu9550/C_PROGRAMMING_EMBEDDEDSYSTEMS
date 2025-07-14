#  Introduction to Pointers in C

##  What is a Pointer?

A **pointer** is a variable that **stores the memory address** of another variable.

In C programming, every variable is stored at a specific memory location, and pointers give you access to that memory address directly.

---

##  Why Use Pointers?

Pointers are used for:
-  **Efficient memory access**
-  **Function parameter passing** (pass-by-reference)
-  **Dynamic memory allocation**
-  **Implementing data structures** like linked lists, trees, graphs
-  **System-level and embedded programming**

---

##  Declaring and Initializing Pointers
###  Syntax:
data_type *pointer_name;

### Example:

int x = 10;
int *ptr = &x;

### Diagrammatic Representation

x = 10;
ptr = &x;

    +--------+           +------------+
x : |   10   |     ptr:  |  address of x (e.g., 0x100) |
    +--------+           +------------+

        ↑
        |
     *ptr = value at address ptr


### Accessing Variable Using Pointer

#include <stdio.h>

int main() {
    int x = 42;
    int *p = &x;

    printf("Value of x: %d\n", x);
    printf("Address of x: %p\n", &x);
    printf("Value in pointer p: %p\n", p);
    printf("Value pointed by p: %d\n", *p);

    return 0;
}

## Sample Output:
- Value of x: 42
- Address of x: 0x7ffeaa4b7a2c
- Value in pointer p: 0x7ffeaa4b7a2c
- Value pointed by p: 42

## Types of Pointers

| Type               | Description                       |
| ------------------ | --------------------------------- |
| `int *p`           | Pointer to `int`                  |
| `char *p`          | Pointer to `char`                 |
| `float *p`         | Pointer to `float`                |
| `double *p`        | Pointer to `double`               |
| `void *p`          | Generic pointer                   |
| `NULL` pointer     | Points to nothing (`NULL` or `0`) |
| Pointer to Pointer | `int **pp` → pointer to a pointer |
