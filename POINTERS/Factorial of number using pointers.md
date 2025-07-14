#  Calculate Factorial Using Pointers in C

This program calculates the **factorial of a number** using a function that accepts pointers as arguments. It demonstrates how to use pointers to modify variables inside a function.

---

## Source Code

```c
#include <stdio.h>

void factorial(int *n, int *fact) {
    *fact = 1;
    for (int i = 1; i <= *n; i++) {
        *fact *= i;
    }
}

int main() {
    int n, fact;
    printf("Enter Number: ");
    scanf("%d", &n);

    factorial(&n, &fact);

    printf("Factorial of %d is: %d\n", n, fact);

    return 0;
}


**Sample Input/Output**
Input:

Enter Number: 5

Output:

Factorial of 5 is: 120
