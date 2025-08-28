# C Program to Check Palindrome Ignoring Spaces, Punctuation, and Case

```c
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int isPalindrome(char str[]) {
    int i = 0, j = strlen(str) - 1;
    while (i < j) {
        while (i < j && !isalnum(str[i])) i++;
        while (i < j && !isalnum(str[j])) j--;
        if (tolower(str[i]) != tolower(str[j]))
            return 0;
        i++;
        j--;
    }
    return 1;
}

int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0'; // Remove newline

    if (isPalindrome(str))
        printf("The string is a palindrome.\n");
    else
        printf("The string is not a palindrome.\n");

    return 0;
}

OUTPUT:
Enter a string: A man, a plan, a canal - Panama!
The string is a palindrome.

Enter a string: Live Evil
The string is a palindrome.
```
# C Program to Check if a String is Palindrome Using Recursion

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int isPalindromeRecursive(char str[], int start, int end) {
    if (start >= end)
        return 1;
    if (tolower(str[start]) != tolower(str[end]))
        return 0;
    return isPalindromeRecursive(str, start + 1, end - 1);
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    int length = strlen(str);
    if (isPalindromeRecursive(str, 0, length - 1))
        printf("The string is a palindrome.\n");
    else
        printf("The string is not a palindrome.\n");

    return 0;
}
 OUTPUT:
Enter a string: radar
The string is a palindrome.

Enter a string: hello
The string is not a palindrome.

