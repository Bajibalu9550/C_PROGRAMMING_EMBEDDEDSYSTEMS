## ✅ Variables in C (Theory)

In **C programming**, a **variable** is a *named location in memory* used to store a value. The value of the variable can be changed during program execution.

---

### 🧠 Features of Variables

* Variables must be declared before use.
* They have a **name**, **data type**, and **value**.
* Variables store **temporary data** in memory.
* They are case-sensitive (`num` and `Num` are different).

---

### 🏷️ Syntax:

```c
data_type variable_name;
```

### 🧪 Example:

```c
int age;
float height;
char grade;
```

You can also assign a value at the time of declaration:

```c
int age = 25;
```

---

### 🧾 Rules for Naming Variables:

1. Can use **letters**, **digits**, and **underscore (`_`)**.
2. Must begin with a **letter** or **underscore**.
3. Cannot be a **C keyword** (`int`, `return`, etc.).
4. Cannot have **spaces** or **special characters** (like `@`, `#`, etc.).

✅ Valid: `count`, `marks_1`, `_total`
❌ Invalid: `1count`, `total#`, `float`

---

### 📦 Types of Variables:

| Type         | Scope                                                                      | Storage      | Lifetime          |
| ------------ | -------------------------------------------------------------------------- | ------------ | ----------------- |
| **Local**    | Inside function/block                                                      | Stack        | Till block ends   |
| **Global**   | Outside all functions                                                      | Data segment | Till program ends |
| **Static**   | Local/global                                                               | Data segment | Till program ends |
| **Register** | Local                                                                      | CPU Register | Till block ends   |
| **Volatile** | Tells compiler to not optimize variable (usually used for hardware access) |              |                   |

---

### 📘 Example Code:

```c
#include <stdio.h>

int globalVar = 100; // Global variable

void demo() {
    int localVar = 50;  // Local variable
    static int staticVar = 1; // Static variable
    printf("Inside function: %d, %d\n", localVar, staticVar);
}

int main() {
    demo();
    printf("Global variable: %d\n", globalVar);
    return 0;
}
```

---
