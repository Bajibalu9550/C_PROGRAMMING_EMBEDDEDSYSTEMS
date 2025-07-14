#  Swap Two Numbers Using Pointers (Without Temporary Variable) in C

This program swaps two integers by using **pointer arguments** and **arithmetic operations** instead of a temporary variable.

---

##  Source Code

```c
#include <stdio.h>

void swap(int *a, int *b) {
    *a = (*a + *b) - (*b = *a);
    printf("In Swap function: a = %d  b = %d\n", *a, *b);
}

int main() {
    int a, b;
    printf("Enter Numbers: ");
    scanf("%d %d", &a, &b);

    printf("In Main Function Before Calling Function:  a = %d  b = %d\n", a, b);
    swap(&a, &b);
    printf("In Main Function After Calling Function:  a = %d  b = %d\n", a, b);

    return 0;
}

 **Sample Input/Output**

Input:

Enter Numbers: 5 10

Output:

In Main Function Before Calling Function:  a = 5  b = 10
In Swap function: a = 10  b = 5
In Main Function After Calling Function:  a = 10  b = 5
