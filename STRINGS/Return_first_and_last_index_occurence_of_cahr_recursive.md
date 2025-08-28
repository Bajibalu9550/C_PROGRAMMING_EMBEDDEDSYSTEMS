# C Program to Find the First and Last Occurrence of a Character in a String Using Recursion

```c
#include <stdio.h>
#include <string.h>

int firstOccurrence(char str[], char ch, int index) {
    if (str[index] == '\0')
        return -1;
    if (str[index] == ch)
        return index;
    return firstOccurrence(str, ch, index + 1);
}

int lastOccurrence(char str[], char ch, int index) {
    if (str[index] == '\0')
        return -1;
    int restIndex = lastOccurrence(str, ch, index + 1);
    if (restIndex != -1)
        return restIndex;
    if (str[index] == ch)
        return index;
    return -1;
}

int main() {
    char str[100];
    char ch;
    printf("Enter a string: ");
    scanf("%s", str);
    printf("Enter character to search: ");
    scanf(" %c", &ch);

    int firstIndex = firstOccurrence(str, ch, 0);
    int lastIndex = lastOccurrence(str, ch, 0);

    printf("First occurrence of '%c': %d\n", ch, firstIndex);
    printf("Last occurrence of '%c': %d\n", ch, lastIndex);

    return 0;
}

OUTPUT:

Enter a string: programming
Enter character to search: g
First occurrence of 'g': 3
Last occurrence of 'g': 10

Enter a string: hello
Enter character to search: l
First occurrence of 'l': 2
Last occurrence of 'l': 3
