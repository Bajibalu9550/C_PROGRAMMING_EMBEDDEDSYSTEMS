# C Program to Convert a String of Numbers to an Integer Using Recursion

```c
#include <stdio.h>

int stringToInt(char str[], int n) {
    if (n == 0)
        return 0;
    int lastDigit = str[n - 1] - '0';
    return stringToInt(str, (n - 1) * 10 + lastDigit);
}

int main() {
    char str[20];
    printf("Enter a string of numbers: ");
    scanf("%s", str);

    int result = stringToInt(str, strlen(str));
    printf("Converted integer: %d\n", result);

    return 0;
}

OUTPUT:
Enter a string of numbers: 12345
Converted integer: 12345
```

# C Program to Convert a String of Numbers to an Integer Using Built-in Function

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char str[20];
    printf("Enter a string of numbers: ");
    scanf("%s", str);

    int num = atoi(str);
    printf("Converted integer: %d\n", num);

    return 0;
}

OUTPUT:
Enter a string of numbers: 12345
Converted integer: 12345
```
# C Program to Convert a String of Numbers to an Integer Using sscanf()

```c
#include <stdio.h>

int main() {
    char str[20];
    int num;
    printf("Enter a string of numbers: ");
    scanf("%s", str);

    sscanf(str, "%d", &num);
    printf("Converted integer: %d\n", num);

    return 0;
}

OUTPUT:
Enter a string of numbers: 6789
Converted integer: 6789



