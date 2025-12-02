## 1. What is meant by structure in c?
- Structure is a user defined data type that allows you to group of different types of data into a single unit.
- A structure is a collection of variables of different data types, grouped together under a single name.
## 2. Why do we need structures?
- Because normal variables can store only one value, and arrays can store only same_type values. but structures allow you to store multiple related values of different data types.
- Example: To store student details -> name, rollno, marks -> all different types.
## 3. What is the syntax of the structure?
```c
struct student{
char name[20];
int rollno;
float marks;
};
```
## 4. When the memory created for structure?
- The Memory creation for a structure is only when you create a structure variable, NOT when you define the structure.

## 5. Where the sttructure memory is allocated?
- This depends on the structure variable creation.
  ### 1. Local structure variable --> Memory created in Stack
  ### 2. Global structure variable --> Memory created in data/bss
  ### 3. Dynamic Structure variable --> Memory created in heap
## 6. What is the life  time and scope of the local structure variable?
- The local structure variable is created in function and its lifetime is: from the moment of the function is called, until the function returns(exits). After the function ends, the memory of structure variable is destroyed automatically.
- The scope of the local structure varibale is limited to the block or function in which it is declared, and it can not be accessed outside that scope.
## 7.  What is the life  time and scope of the global structure variable?
- A global structure variable has static lifetime: it is created when the program starts and destroyed when the program ends. Its scope extends from the point of declaration to the end of the file, and it can be accessed by any function within that file, It can also be acceessed from other files usinf extern keyword.
  
