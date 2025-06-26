# Data Types in C

In **C programming**, **data types** are used to declare variables and functions. A data type tells the compiler:

- **What kind of data** (e.g., integer, character, floating-point, etc.) is stored.
- **How much memory** to allocate.
- **How to interpret the bit pattern** stored in memory.

---

## 1. Fundamental (Basic) Data Types

These are the standard types provided by C:

| **Type**   | **Meaning**                                 |
|------------|---------------------------------------------|
| `int`      | Used to store integer values (whole numbers) |
| `float`    | Used to store single-precision decimal numbers |
| `double`   | Used to store double-precision decimal numbers |
| `char`     | Used to store a single character             |
| `void`     | Represents “no value” or “nothing”           |

---

## 2. Derived Data Types

These types are based on the basic types:

- **Array**: A collection of elements of the same type.  
  Example: `int arr[10];`
  
- **Pointer**: A variable that stores the memory address of another variable.  
  Example: `int *ptr;`
  
- **Function**: A block of code that performs a specific task and may return a value.  
  Example: `int sum(int a, int b);`
  
- **Structure**: A user-defined type that groups variables of different types.  
  Example: `struct Person { int age; char name[20]; };`
  
- **Union**: Similar to structure but shares memory between all members.  
  Example: `union Data { int i; float f; };`

---

## 3. User-Defined Data Types

These are custom types created by the user using C keywords:

- `struct`: Combines variables of different types into a single unit.
- `union`: Similar to `struct`, but with shared memory.
- `enum`: Defines a list of named integer constants.
- `typedef`: Creates a new name (alias) for an existing type.

---

## 4. Type Modifiers

Modifiers are keywords used to alter the size or range of data types:

| Modifier     | Purpose                                      |
|--------------|----------------------------------------------|
| `signed`     | Allows both positive and negative values     |
| `unsigned`   | Allows only positive values                  |
| `short`      | Reduces the size (and range) of the variable |
| `long`       | Increases the size (and range)               |

Example:
```c
short int a;       // smaller integer
long int b;        // larger integer
unsigned int c;    // positive only integer
```

---

## 5. Memory Size and Range (Typical for 32-bit systems)

| **Data Type** | **Size (Bytes)** | **Range**                         |
|---------------|------------------|-----------------------------------|
| `char`        | 1 byte           | -128 to 127 (signed)              |
| `int`         | 4 bytes          | -2,147,483,648 to 2,147,483,647   |
| `float`       | 4 bytes          | ~ ±3.4 × 10^38 (6 decimal places) |
| `double`      | 8 bytes          | ~ ±1.7 × 10^308 (15 decimal places) |
| `void`        | 0 bytes          | No value                          |

> **Note**: Sizes may vary with architecture and compiler (e.g., 64-bit).

---

## Summary

- Data types are essential for declaring variables correctly.
- They define how data is stored, accessed, and manipulated.
- C supports fundamental, derived, and user-defined data types.
- Type modifiers help expand or limit data type capabilities.
