# Program to send a function ‘s address as an argument to other function. 

```
#include <stdio.h>

int multiply(int a, int b) {
    return a * b;
}

void execute(int (*func)(int, int), int x, int y) {
    int result = func(x, y);
    printf("Result is: %d\n", result);
}

int main() {
    int a = 5, b = 6;
    execute(multiply, a, b);
    return 0;
}

```

__OUTPUT :__

Result is: 30
