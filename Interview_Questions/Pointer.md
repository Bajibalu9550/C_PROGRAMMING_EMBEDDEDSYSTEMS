## 1. What is meant by pointer. What is the size of pointer.?

- A pointer is a variable which is used to store the address of another variable insted of value.
- By using pointers we can store the address of the normal variables(int,char,float,double), address of array, address of dynamically allocated memory,etc..
- By using pointers we can implement the call by reference.
- The sizeof the  pointer is Based on the os.
   - If os is 32bit then size of the any pointer is 4Bytes.
   - If os is 64bit then the size of the any pointe is 8Bytes,
## 2. What is meant by void pointer?
- The void pointer is also called generic pointer.
- By using void pointer we can store any types of address like int,char,float
- The void pointer must be typecasting with appropriate datatype when dereferencing.
```c
#include <stdio.h>

int main() {
    int a = 10;
    float b = 5.5;
    char c = 'X';

    void *ptr;

    ptr = &a;
    printf("Integer value = %d\n", *(int *)ptr);

    ptr = &b;
    printf("Float value = %.2f\n", *(float *)ptr);

    ptr = &c;
    printf("Char value = %c\n", *(char *)ptr);

    return 0;
}

```
## 3. What is meant by wild pointer?
- The wild pointer is nothing but the pointer is declared but not initialized with valid address and not point to any valid memory location.
```c
#include <stdio.h>

int main() {
    int *p;   //  Wild pointer (uninitialized)

    *p = 10;  // Dangerous: writing to unknown memory

    return 0;
}

```
## 4. What is meant by Dangling pointer?
- Dangling pointer is nothing but the pointer pointing to memory location that has been already freed,deleted out of scope.
- If you try to dereference pointer after free then the behaviour is undefined.
- To overcome this undefined behaviour, assign NULL to pointer.
- Dangling pointer will create in two cases:
  1. __Dangling Pointer after free().__
  2. __Dangling Pointer due to local variable out of scope__

#### 1. Dangling Poinnter after free()
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *p = (int *)malloc(sizeof(int));
    *p = 20;

    free(p);  // Memory freed

    printf("%d\n", *p);  // Dangling pointer (dangerous)
    return 0;
}

```
- Assign NULL to pointer to avoid dangling pointer.
  
#### 2. Dangling Pointer due to local variable out of scope
```c
int* getPointer() {
    int x = 100;  // Local variable
    return &x;    //  x destroyed when function ends
}

int main() {
    int *p = getPointer();
    printf("%d\n", *p);  //  Dangling pointer
}

```
- Use static or dynamic memory allocation to avoid dangling pointer due to local variable

## 5. What is function pointer?
- Function pointer is nothing but pointer used to store the address of function.
- Syntax of function pointer is:
  ```
  return_type (*pointer_name)(arg_types);
  ```
- Example:
```c
#include <stdio.h>

void hello() {
    printf("Hello Balu!\n");
}

int main() {
    void (*fp)();   // function pointer declaration
    fp = hello;     // assign function address
    fp();           // call function through pointer
    return 0;
}

```
## 6. What is fuction pointer array?
- A fucnction pointer array is an array where each element is a pointer to function. It stores the address of fucnction.
- Syntax:
```
return_type(*function_pointer[]) (argument_list);
```

## 7. Can a pointer return from function.?
- Yes but,

  - If the pointer is pointing to local variable then it becomes dangerous.
  - If the pointer is pointing to static or heap memory then it is safe.
## 8. What is meant by poniter aliasing?
- If two pointers are pointing to same memory location then it is called pointer aliasing.

## 9. How can ik free the dynamically allocated memory without using free()?
- We can free by using realloc() function

```
ptr=realloc(ptr,0);

ptr = address of the memory which is created by malloc or calloc
```
