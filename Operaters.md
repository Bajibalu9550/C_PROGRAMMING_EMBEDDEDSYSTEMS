# Operators in C – Full Theory with Examples

##  1. Arithmetic Operators

These operators perform **basic mathematical operations**.

| Operator | Meaning       | Example   | Explanation                             |
|----------|----------------|-----------|-----------------------------------------|
| `+`      | Addition       | `a + b`   | Adds `a` and `b`                        |
| `-`      | Subtraction    | `a - b`   | Subtracts `b` from `a`                  |
| `*`      | Multiplication | `a * b`   | Multiplies `a` and `b`                  |
| `/`      | Division       | `a / b`   | Divides `a` by `b` (integer division)   |
| `%`      | Modulus        | `a % b`   | Remainder of `a` divided by `b`         |

###  Example
```c
int a = 10, b = 3;
printf("%d\n", a + b); // 13
printf("%d\n", a - b); // 7
printf("%d\n", a * b); // 30
printf("%d\n", a / b); // 3
printf("%d\n", a % b); // 1
```

---

##  2. Relational (Comparison) Operators

Used to **compare two values**.

| Operator | Meaning            | Example      | Explanation                        |
|----------|--------------------|--------------|------------------------------------|
| `==`     | Equal to           | `a == b`     | True if `a` equals `b`             |
| `!=`     | Not equal to       | `a != b`     | True if `a` is not equal to `b`    |
| `>`      | Greater than       | `a > b`      | True if `a` > `b`                  |
| `<`      | Less than          | `a < b`      | True if `a` < `b`                  |
| `>=`     | Greater or equal   | `a >= b`     | True if `a` >= `b`                 |
| `<=`     | Less or equal      | `a <= b`     | True if `a` <= `b`                 |

###  Example
```c
int a = 5, b = 10;
printf("%d\n", a < b);  // 1
printf("%d\n", a == b); // 0
```

---

##  3. Logical Operators

Used to **combine or invert conditions**.

| Operator | Name         | Description                                      |
|----------|--------------|--------------------------------------------------|
| `&&`     | Logical AND  | True if **both** conditions are true             |
| `||`     | Logical OR   | True if **at least one** condition is true       |
| `!`      | Logical NOT  | Inverts the result (true becomes false)          |

###  Example
```c
int a = 5, b = 10;
printf("%d\n", (a < b) && (a > 0));  
printf("%d\n", (a > b) || (a == 5)); 
printf("%d\n", !(a == 5));           
```

---

##  4. Assignment Operators

Used to **assign or modify values**.

| Operator | Meaning             | Equivalent To    |
|----------|----------------------|------------------|
| `=`      | Assign               | `a = 5`          |
| `+=`     | Add and assign       | `a = a + 5`      |
| `-=`     | Subtract and assign  | `a = a - 5`      |
| `*=`     | Multiply and assign  | `a = a * 5`      |
| `/=`     | Divide and assign    | `a = a / 5`      |
| `%=`     | Modulus and assign   | `a = a % 5`      |

###  Example
```c
int a = 10;
a += 5;
a *= 2;
a %= 7;
```

---

##  5. Increment and Decrement Operators

Used to **increase or decrease a value by 1**.

| Operator | Type           | Meaning                                    |
|----------|----------------|--------------------------------------------|
| `++a`    | Pre-increment  | Increases first, then uses the new value   |
| `a++`    | Post-increment | Uses value, then increases it              |
| `--a`    | Pre-decrement  | Decreases first, then uses it              |
| `a--`    | Post-decrement | Uses it, then decreases                    |

###  Example
```c
int a = 5;
printf("%d\n", a++); // 5 then a = 6
printf("%d\n", ++a); // a = 7
```

---

##  6. Bitwise Operators

Operate directly on bits.

| Operator | Meaning        | Example | Explanation                        |
|----------|----------------|---------|------------------------------------|
| `&`      | AND            | 5 & 3   | 0101 & 0011 = 0001 → 1             |
| `|`      | OR             | 5 | 3   | 0101 | 0011 = 0111 → 7             |
| `^`      | XOR            | 5 ^ 3   | 0101 ^ 0011 = 0110 → 6             |
| `~`      | NOT            | ~5      | Bitwise complement                 |
| `<<`     | Left shift     | a << 1  | Multiplies by 2                    |
| `>>`     | Right shift    | a >> 1  | Divides by 2                       |

###  Example
```c
int a = 5, b = 3;
printf("%d\n", a & b);
printf("%d\n", a | b);
printf("%d\n", a ^ b);
printf("%d\n", ~a);
```

---

##  7. Conditional (Ternary) Operator

Shorthand for `if-else`.

###  Syntax
```c
(condition) ? true_value : false_value;
```

###  Example
```c
int a = 10, b = 20;
int max = (a > b) ? a : b;
```

---

##  8. Special Operators

| Operator | Description                           |
|----------|---------------------------------------|
| `sizeof` | Gets size of a type                   |
| `&`      | Gets address of variable              |
| `*`      | Dereferences pointer                  |
| `.`      | Access structure member               |
| `->`     | Access member via pointer to struct   |

###  Example
```c
struct Student {
    int id;
};
struct Student s = {1};
struct Student *p = &s;
printf("%d\n", s.id);
printf("%d\n", p->id);
```

---

##  9. Comma Operator

Allows multiple expressions. Returns the last one.

###  Example
```c
int a;
a = (1, 2, 3); // a = 3
```
