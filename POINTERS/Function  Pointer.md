#  Function Pointer in C

##  What is a Function Pointer?

A **function pointer** is a pointer that stores the **address of a function**. Unlike data pointers, which point to variables, function pointers allow functions to be called **indirectly**.

---

##  Why Use Function Pointers?

Function pointers are useful for:
- **Callback functions**
- **Dynamic function calling** at runtime
- **Arrays of functions** (like switch-case or menus)
- **Implementing polymorphism-like behavior in C**

---

Syntax

```c
return_type (*pointer_name)(parameter_list);

 Example:

int (*fp)(int, int);


 Example Code

#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int main() {
    int (*fp)(int, int);  // declare function pointer
    fp = add;             // assign function's address
    printf("%d\n", (*fp)(5, 3));  // call function via pointer
    return 0;
}
