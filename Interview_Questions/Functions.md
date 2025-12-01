## 1. What is meant by function and types?
- Function is a block of code that perform some specific task.
- You write is once and you can call it many times.
- Functions are two types:

  - Predefined Functions
  - User defined functios
#### Predefined Functions:
- Pre-defined functions are the functions that are already written and provided by the C Standard library. You don't havr to write them - you simply include the header file and use them.
- Their internal implementation is already writte in C Standard Library.
  ##### Example:
  - printf()
  - scanf()
  - strlen()
  - sqrt()
  - malloc()
#### User-defined Functions:
- User-defined functions are functions those are created by user to perform some specific task.
- Types of user defined funcntios: 4 types

  - No arguments, no return value
  - No arguments, with return value
  - With arguments, no return value
  - With arguments, with return value
## 2. What are the function prototypes?
- Return type
- Function name
- Parameter & type.
## 3. Can a function return multiple values?
- Directly is not possible.
- But you can use: Pointers, structures , arrays, Returning pointer to array.
## 4. What is meant by recursion>
- A function call itself until base condition met.

## 5. What  is meant by Tail Recursion?
- When a recursive call is the last statememnt of the function. that recursion is called Tail Recursion.
```c
int func(int n,int a){
if(n==0){
retur a;
}
return fun(n-1,a+n);               // Tail Recursion
}

```

## 6. Can a function return a function?
- When a function returns another functor. it means the outer function produces a new function as its result. This returned function can be later, possibly with different arguments.
```c
#include<stdio.h>
int add(int x,int y){
return x+y:
}
int (*(getfun())(){
return add;
}

int main(){
int (*fp)()=getfun();
printf("%d\n",fp(3,4));
```

## 7. Can we pass a function as an argument to another function?

- Yes we can pass function as argument to the another function. by using function pointer.


```c
void hello(){
printf("Hello world!");
}

void callfun(Void *(fp)()){   // Function Pointer
fp();   // Call the function
}
int main(){
callfun(hello);    // Passing function as an argument
}

```

## 8. What is meant by call back function?
- A function passsed as an argument to anothet function is called call back function
