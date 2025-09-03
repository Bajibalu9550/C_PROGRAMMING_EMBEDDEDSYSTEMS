# C Program to Add Two Complex Numbers Using Structures

```c
#include <stdio.h>

struct Complex {
    float real;
    float imag;
};

struct Complex addComplex(struct Complex c1, struct Complex c2) {
    struct Complex result;
    result.real = c1.real + c2.real;
    result.imag = c1.imag + c2.imag;
    return result;
}

int main() {
    struct Complex num1, num2, sum;

    printf("Enter real and imaginary parts of first complex number: ");
    scanf("%f %f", &num1.real, &num1.imag);

    printf("Enter real and imaginary parts of second complex number: ");
    scanf("%f %f", &num2.real, &num2.imag);

    sum = addComplex(num1, num2);

    printf("Sum of the complex numbers: %.2f + %.2fi\n", sum.real, sum.imag);

    return 0;
}


OUTPUT:

Enter real and imaginary parts of first complex number: 2 3
Enter real and imaginary parts of second complex number: 4 5
Sum of the complex numbers: 6.00 + 8.00i
```
