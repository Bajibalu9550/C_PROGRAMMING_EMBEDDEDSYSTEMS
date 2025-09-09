
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



