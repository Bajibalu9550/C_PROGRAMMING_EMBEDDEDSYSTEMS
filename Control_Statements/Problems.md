1) Accept two integers and check whether they are equal or not

```
#include <stdio.h>
int main() {
    int a, b;
    printf("Enter two integers: ");
    scanf("%d %d", &a, &b);
    if (a == b)
        printf("Both are equal\n");
    else
        printf("Not equal\n");
    return 0;
}
```
2) Check whether a number is even or odd
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);
    if (n % 2 == 0)
        printf("Even\n");
    else
        printf("Odd\n");
    return 0;
}
```
3) Check whether a number is positive or negative
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);
    if (n > 0)
        printf("Positive\n");
    else if (n < 0)
        printf("Negative\n");
    else
        printf("Zero\n");
    return 0;
}
```
4) Check whether a year is leap year or not
```
#include <stdio.h>
int main() {
    int year;
    printf("Enter year: ");
    scanf("%d", &year);
    if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0))
        printf("Leap Year\n");
    else
        printf("Not Leap Year\n");
    return 0;
}
```
5) Check whether candidate is eligible to vote
```
#include <stdio.h>
int main() {
    int age;
    printf("Enter age: ");
    scanf("%d", &age);
    if (age >= 18)
        printf("Eligible to vote\n");
    else
        printf("Not eligible\n");
    return 0;
}
```
6) Display value of N depending on M
```
#include <stdio.h>
int main() {
    int m, n;
    printf("Enter value of M: ");
    scanf("%d", &m);
    if (m > 0) n = 1;
    else if (m == 0) n = 0;
    else n = -1;
    printf("N = %d\n", n);
    return 0;
}
```
7) Find largest of three numbers
```
#include <stdio.h>
int main() {
    int a, b, c;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);
    if (a >= b && a >= c)
        printf("Largest = %d\n", a);
    else if (b >= a && b >= c)
        printf("Largest = %d\n", b);
    else
        printf("Largest = %d\n", c);
    return 0;
}
```
8) Check whether a character is vowel or consonant
```
#include <stdio.h>
int main() {
    char ch;
    printf("Enter a character: ");
    scanf(" %c", &ch);
    if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'||
        ch=='A'||ch=='E'||ch=='I'||ch=='O'||ch=='U')
        printf("Vowel\n");
    else
        printf("Consonant\n");
    return 0;
}
```
9) Check whether a character is alphabet or not
```
#include <stdio.h>
int main() {
    char ch;
    printf("Enter character: ");
    scanf(" %c", &ch);
    if ((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z'))
        printf("Alphabet\n");
    else
        printf("Not Alphabet\n");
    return 0;
}
```
10) Find minimum or maximum between two numbers
```
#include <stdio.h>
int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    if (a > b)
        printf("Max = %d, Min = %d\n", a, b);
    else
        printf("Max = %d, Min = %d\n", b, a);
    return 0;
}
```
11) Enter week number and print day of week
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter week number (1–7): ");
    scanf("%d", &n);
    switch(n) {
        case 1: printf("Sunday\n"); break;
        case 2: printf("Monday\n"); break;
        case 3: printf("Tuesday\n"); break;
        case 4: printf("Wednesday\n"); break;
        case 5: printf("Thursday\n"); break;
        case 6: printf("Friday\n"); break;
        case 7: printf("Saturday\n"); break;
        default: printf("Invalid\n");
    }
    return 0;
}
```
12) Check whether a character is uppercase or lowercase
```
#include <stdio.h>
int main() {
    char ch;
    printf("Enter character: ");
    scanf(" %c", &ch);
    if (ch >= 'A' && ch <= 'Z')
        printf("Uppercase\n");
    else if (ch >= 'a' && ch <= 'z')
        printf("Lowercase\n");
    else
        printf("Not Alphabet\n");
    return 0;
}
```
13) Find number of days in a month
```
#include <stdio.h>
int main() {
    int month;
    printf("Enter month (1–12): ");
    scanf("%d", &month);
    switch(month) {
        case 1: case 3: case 5: case 7: case 8: case 10: case 12:
            printf("31 days\n"); break;
        case 4: case 6: case 9: case 11:
            printf("30 days\n"); break;
        case 2:
            printf("28 or 29 days\n"); break;
        default:
            printf("Invalid month\n");
    }
    return 0;
}
```
14) Find maximum between two numbers using switch case
```
#include <stdio.h>
int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    switch(a > b) {
        case 1: printf("Max = %d\n", a); break;
        case 0: printf("Max = %d\n", b); break;
    }
    return 0;
}
```
15) Print even numbers between 1 to 20 using for loop
```
#include <stdio.h>
int main() {
    for (int i = 2; i <= 20; i += 2)
        printf("%d ", i);
    return 0;
}
```
16) Calculate sum of numbers from 1 to 100 using while loop
```
#include <stdio.h>
int main() {
    int i = 1, sum = 0;
    while (i <= 100) {
        sum += i;
        i++;
    }
    printf("Sum = %d\n", sum);
    return 0;
}
```
17) Find factorial of a given number using for loop
```
#include <stdio.h>
int main() {
    int n, fact = 1;
    printf("Enter number: ");
    scanf("%d", &n);
    for (int i = 1; i <= n; i++)
        fact *= i;
    printf("Factorial = %d\n", fact);
    return 0;
}
```
18) Check whether a number is prime or not using while loop
```
#include <stdio.h>
int main() {
    int n, i = 2, flag = 1;
    printf("Enter number: ");
    scanf("%d", &n);
    if (n <= 1) flag = 0;
    while (i <= n/2) {
        if (n % i == 0) {
            flag = 0;
            break;
        }
        i++;
    }
    if (flag) printf("Prime\n");
    else printf("Not Prime\n");
    return 0;
}
```
19) Find sum of digits of a number using while loop
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter number: ");
    scanf("%d", &n);
    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }
    printf("Sum of digits = %d\n", sum);
    return 0;
}
```
20) Print Fibonacci series up to N terms using for loop
```
#include <stdio.h>
int main() {
    int n, a = 0, b = 1, next;
    printf("Enter terms: ");
    scanf("%d", &n);
    for (int i = 1; i <= n; i++) {
        printf("%d ", a);
        next = a + b;
        a = b;
        b = next;
    }
    return 0;
}
```
21) Reverse a given number using while loop
```
#include <stdio.h>
int main() {
    int n, rev = 0;
    printf("Enter number: ");
    scanf("%d", &n);
    while (n != 0) {
        rev = rev * 10 + (n % 10);
        n /= 10;
    }
    printf("Reversed = %d\n", rev);
    return 0;
}
```


22) Find the largest element in an array using a for loop

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    int max = a[0];
    for (int i = 1; i < n; i++) {
        if (a[i] > max) max = a[i];
    }
    printf("Largest = %d\n", max);
    return 0;
}
```
23) Find the smallest element in an array using a while loop
```
#include <stdio.h>
int main() {
    int n, i = 0;
    printf("Enter size of array: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int j = 0; j < n; j++) scanf("%d", &a[j]);
    int min = a[0];
    while (i < n) {
        if (a[i] < min) min = a[i];
        i++;
    }
    printf("Smallest = %d\n", min);
    return 0;
}
```
24) Print all elements of an array using a for loop
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    printf("Array elements: ");
    for (int i = 0; i < n; i++) printf("%d ", a[i]);
    return 0;
}
```
25) Find the sum of elements in an array using a while loop
```
#include <stdio.h>
int main() {
    int n, i = 0, sum = 0;
    printf("Enter size of array: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int j = 0; j < n; j++) scanf("%d", &a[j]);
    while (i < n) {
        sum += a[i];
        i++;
    }
    printf("Sum = %d\n", sum);
    return 0;
}
```
26) Count the number of vowels in a string using a for loop
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    int count = 0;
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    for (int i = 0; i < strlen(str); i++) {
        char ch = str[i];
        if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'||
            ch=='A'||ch=='E'||ch=='I'||ch=='O'||ch=='U')
            count++;
    }
    printf("Vowels = %d\n", count);
    return 0;
}
```
27) Count the number of words in a string using a while loop
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200];
    int i = 0, words = 1;
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    while (str[i] != '\0') {
        if (str[i] == ' ' || str[i] == '\n') words++;
        i++;
    }
    printf("Words = %d\n", words);
    return 0;
}
```
28) Check whether a string is palindrome using a for loop
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    int flag = 1;
    printf("Enter string: ");
    scanf("%s", str);
    int len = strlen(str);
    for (int i = 0; i < len/2; i++) {
        if (str[i] != str[len-1-i]) {
            flag = 0;
            break;
        }
    }
    if (flag) printf("Palindrome\n");
    else printf("Not Palindrome\n");
    return 0;
}
```
29) Concatenate two strings without library functions using a while loop
```
#include <stdio.h>
int main() {
    char str1[100], str2[100];
    int i = 0, j = 0;
    printf("Enter first string: ");
    scanf("%s", str1);
    printf("Enter second string: ");
    scanf("%s", str2);
    while (str1[i] != '\0') i++;
    while (str2[j] != '\0') {
        str1[i] = str2[j];
        i++; j++;
    }
    str1[i] = '\0';
    printf("Concatenated = %s\n", str1);
    return 0;
}
```
30) Find the length of a string using a for loop
```
#include <stdio.h>
int main() {
    char str[100];
    int len = 0;
    printf("Enter string: ");
    scanf("%s", str);
    for (int i = 0; str[i] != '\0'; i++) len++;
    printf("Length = %d\n", len);
    return 0;
}
```
31) Convert a string to uppercase using a while loop
```
#include <stdio.h>
int main() {
    char str[100];
    int i = 0;
    printf("Enter string: ");
    scanf("%s", str);
    while (str[i] != '\0') {
        if (str[i] >= 'a' && str[i] <= 'z')
            str[i] -= 32;
        i++;
    }
    printf("Uppercase = %s\n", str);
    return 0;
}
```
32) Find the power of a number using a for loop
```
#include <stdio.h>
int main() {
    int base, exp, result = 1;
    printf("Enter base and exponent: ");
    scanf("%d %d", &base, &exp);
    for (int i = 1; i <= exp; i++)
        result *= base;
    printf("Power = %d\n", result);
    return 0;
}
```
33) Find the factorial of a number using a while loop
```
#include <stdio.h>
int main() {
    int n, fact = 1;
    printf("Enter number: ");
    scanf("%d", &n);
    while (n > 0) {
        fact *= n;
        n--;
    }
    printf("Factorial = %d\n", fact);
    return 0;
}
```
34) Find the GCD of two numbers using a while loop
```
#include <stdio.h>
int main() {
    int a, b;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    while (a != b) {
        if (a > b) a -= b;
        else b -= a;
    }
    printf("GCD = %d\n", a);
    return 0;
}
```
35) Find the LCM of two numbers using a for loop
```
#include <stdio.h>
int main() {
    int a, b, lcm;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    for (lcm = (a > b ? a : b); ; lcm++) {
        if (lcm % a == 0 && lcm % b == 0) break;
    }
    printf("LCM = %d\n", lcm);
    return 0;
}
```
36) Print multiplication table of a number using a for loop
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);
    for (int i = 1; i <= 10; i++)
        printf("%d x %d = %d\n", n, i, n*i);
    return 0;
}
```
37) Print Armstrong numbers between 1 and 1000 using a for loop
```
#include <stdio.h>
#include <math.h>
int main() {
    for (int n = 1; n <= 1000; n++) {
        int temp = n, sum = 0, digits = 0;
        int x = n;
        while (x != 0) { digits++; x /= 10; }
        x = n;
        while (x != 0) {
            sum += pow(x % 10, digits);
            x /= 10;
        }
        if (sum == n) printf("%d ", n);
    }
    return 0;
}
```
38) Implement a simple calculator using switch-case
```
#include <stdio.h>
int main() {
    char op;
    int a, b;
    printf("Enter operator (+,-,*,/): ");
    scanf(" %c", &op);
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    switch(op) {
        case '+': printf("Sum = %d\n", a+b); break;
        case '-': printf("Diff = %d\n", a-b); break;
        case '*': printf("Product = %d\n", a*b); break;
        case '/': 
            if (b != 0) printf("Quotient = %d\n", a/b);
            else printf("Division by zero\n");
            break;
        default: printf("Invalid operator\n");
    }
    return 0;
}
```
39) Check whether a number is palindrome using while loop and if-else
```
#include <stdio.h>
int main() {
    int n, rev = 0, temp;
    printf("Enter number: ");
    scanf("%d", &n);
    temp = n;
    while (temp != 0) {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }
    if (n == rev) printf("Palindrome\n");
    else printf("Not Palindrome\n");
    return 0;
}
```
40) Find the sum of elements in the lower triangular matrix
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter order of matrix: ");
    scanf("%d", &n);
    int a[n][n], sum = 0;
    printf("Enter elements:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);
    for (int i = 0; i < n; i++) {
        for (int j = 0; j <= i; j++) sum += a[i][j];
    }
    printf("Sum of lower triangular = %d\n", sum);
    return 0;
}
```
41) Find the sum of elements in the upper triangular matrix
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter order of matrix: ");
    scanf("%d", &n);
    int a[n][n], sum = 0;
    printf("Enter elements:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);
    for (int i = 0; i < n; i++) {
        for (int j = i; j < n; j++) sum += a[i][j];
    }
    printf("Sum of upper triangular = %d\n", sum);
    return 0;
}
```
42) Remove duplicate elements from an array using loops and if-else
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    int b[n], k = 0;
    for (int i = 0; i < n; i++) {
        int duplicate = 0;
        for (int j = 0; j < k; j++) {
            if (a[i] == b[j]) {
                duplicate = 1;
                break;
            }
        }
        if (!duplicate) b[k++] = a[i];
    }
    printf("Array without duplicates: ");
    for (int i = 0; i < k; i++) printf("%d ", b[i]);
    return 0;
}
```
 43) Sort an array in ascending order using loops and if-else

```
#include <stdio.h>
int main() {
    int n, temp;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);

    for (int i = 0; i < n-1; i++) {
        for (int j = i+1; j < n; j++) {
            if (a[i] > a[j]) {
                temp = a[i];
                a[i] = a[j];
                a[j] = temp;
            }
        }
    }

    printf("Ascending order: ");
    for (int i = 0; i < n; i++) printf("%d ", a[i]);
    return 0;
}
```
44) Sort an array in descending order using loops and if-else
```
#include <stdio.h>
int main() {
    int n, temp;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);

    for (int i = 0; i < n-1; i++) {
        for (int j = i+1; j < n; j++) {
            if (a[i] < a[j]) {
                temp = a[i];
                a[i] = a[j];
                a[j] = temp;
            }
        }
    }

    printf("Descending order: ");
    for (int i = 0; i < n; i++) printf("%d ", a[i]);
    return 0;
}
```
45) Find the second largest element in an array
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);

    int max1 = a[0], max2 = -1e9;
    for (int i = 1; i < n; i++) {
        if (a[i] > max1) {
            max2 = max1;
            max1 = a[i];
        } else if (a[i] > max2 && a[i] != max1) {
            max2 = a[i];
        }
    }

    printf("Second largest = %d\n", max2);
    return 0;
}
```
46) Find the frequency of each element in an array
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n], freq[n];

    printf("Enter elements: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        freq[i] = -1;
    }

    for (int i = 0; i < n; i++) {
        if (freq[i] == -1) {
            int count = 1;
            for (int j = i+1; j < n; j++) {
                if (a[i] == a[j]) {
                    count++;
                    freq[j] = 0;
                }
            }
            freq[i] = count;
        }
    }

    printf("Frequencies:\n");
    for (int i = 0; i < n; i++) {
        if (freq[i] > 0) printf("%d -> %d\n", a[i], freq[i]);
    }
    return 0;
}
```
47) Check whether a matrix is an identity matrix
```
#include <stdio.h>
int main() {
    int n, flag = 1;
    printf("Enter order: ");
    scanf("%d", &n);
    int a[n][n];
    printf("Enter matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if ((i == j && a[i][j] != 1) || (i != j && a[i][j] != 0)) {
                flag = 0;
                break;
            }
        }
    }

    if (flag) printf("Identity matrix\n");
    else printf("Not identity matrix\n");
    return 0;
}
```
48) Print odd numbers between 1 to 50 using a for loop
```
#include <stdio.h>
int main() {
    for (int i = 1; i <= 50; i++) {
        if (i % 2 != 0) printf("%d ", i);
    }
    return 0;
}
```
49) Find the sum of elements in each column of a matrix
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c];
    printf("Enter matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    for (int j = 0; j < c; j++) {
        int sum = 0;
        for (int i = 0; i < r; i++) sum += a[i][j];
        printf("Sum of column %d = %d\n", j+1, sum);
    }
    return 0;
}
```
50) Find the sum of elements in each row of a matrix
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c];
    printf("Enter matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    for (int i = 0; i < r; i++) {
        int sum = 0;
        for (int j = 0; j < c; j++) sum += a[i][j];
        printf("Sum of row %d = %d\n", i+1, sum);
    }
    return 0;
}
```
51) Add two matrices
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c], b[r][c], sum[r][c];
    printf("Enter first matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);
    printf("Enter second matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &b[i][j]);

    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            sum[i][j] = a[i][j] + b[i][j];
            printf("%d ", sum[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
52) Subtract two matrices
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c], b[r][c], diff[r][c];
    printf("Enter first matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);
    printf("Enter second matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &b[i][j]);

    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            diff[i][j] = a[i][j] - b[i][j];
            printf("%d ", diff[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
53) Multiply two matrices
```
#include <stdio.h>
int main() {
    int r1, c1, r2, c2;
    printf("Enter rows & cols of first matrix: ");
    scanf("%d %d", &r1, &c1);
    printf("Enter rows & cols of second matrix: ");
    scanf("%d %d", &r2, &c2);

    if (c1 != r2) {
        printf("Multiplication not possible\n");
        return 0;
    }

    int a[r1][c1], b[r2][c2], mul[r1][c2];
    printf("Enter first matrix:\n");
    for (int i = 0; i < r1; i++)
        for (int j = 0; j < c1; j++)
            scanf("%d", &a[i][j]);

    printf("Enter second matrix:\n");
    for (int i = 0; i < r2; i++)
        for (int j = 0; j < c2; j++)
            scanf("%d", &b[i][j]);

    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            mul[i][j] = 0;
            for (int k = 0; k < c1; k++)
                mul[i][j] += a[i][k] * b[k][j];
            printf("%d ", mul[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
54) Print elements of an array in reverse order
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    printf("Reverse: ");
    for (int i = n-1; i >= 0; i--) printf("%d ", a[i]);
    return 0;
}
```
55) Check whether two arrays are equal or not
```
#include <stdio.h>
int main() {
    int n, flag = 1;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n], b[n];
    printf("Enter first array: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    printf("Enter second array: ");
    for (int i = 0; i < n; i++) scanf("%d", &b[i]);

    for (int i = 0; i < n; i++) {
        if (a[i] != b[i]) {
            flag = 0;
            break;
        }
    }

    if (flag) printf("Arrays are equal\n");
    else printf("Arrays are not equal\n");
    return 0;
}
```
56) Find the union of two arrays
```
#include <stdio.h>
int main() {
    int n1, n2;
    printf("Enter size of first array: ");
    scanf("%d", &n1);
    int a[n1];
    printf("Enter elements: ");
    for (int i = 0; i < n1; i++) scanf("%d", &a[i]);

    printf("Enter size of second array: ");
    scanf("%d", &n2);
    int b[n2];
    printf("Enter elements: ");
    for (int i = 0; i < n2; i++) scanf("%d", &b[i]);

    int c[n1+n2], k = 0;
    for (int i = 0; i < n1; i++) c[k++] = a[i];
    for (int i = 0; i < n2; i++) {
        int found = 0;
        for (int j = 0; j < n1; j++) {
            if (b[i] == a[j]) { found = 1; break; }
        }
        if (!found) c[k++] = b[i];
    }

    printf("Union: ");
    for (int i = 0; i < k; i++) printf("%d ", c[i]);
    return 0;
}
```
57) Find the intersection of two arrays
```
#include <stdio.h>
int main() {
    int n1, n2;
    printf("Enter size of first array: ");
    scanf("%d", &n1);
    int a[n1];
    printf("Enter elements: ");
    for (int i = 0; i < n1; i++) scanf("%d", &a[i]);

    printf("Enter size of second array: ");
    scanf("%d", &n2);
    int b[n2];
    printf("Enter elements: ");
    for (int i = 0; i < n2; i++) scanf("%d", &b[i]);

    printf("Intersection: ");
    for (int i = 0; i < n1; i++) {
        for (int j = 0; j < n2; j++) {
            if (a[i] == b[j]) {
                printf("%d ", a[i]);
                break;
            }
        }
    }
    return 0;
}
```
58) Find the difference of two arrays (A - B)
```
#include <stdio.h>
int main() {
    int n1, n2;
    printf("Enter size of first array: ");
    scanf("%d", &n1);
    int a[n1];
    printf("Enter elements: ");
    for (int i = 0; i < n1; i++) scanf("%d", &a[i]);

    printf("Enter size of second array: ");
    scanf("%d", &n2);
    int b[n2];
    printf("Enter elements: ");
    for (int i = 0; i < n2; i++) scanf("%d", &b[i]);

    printf("Difference (A - B): ");
    for (int i = 0; i < n1; i++) {
        int found = 0;
        for (int j = 0; j < n2; j++) {
            if (a[i] == b[j]) { found = 1; break; }
        }
        if (!found) printf("%d ", a[i]);
    }
    return 0;
}
```
59) Find the missing number in an array containing 1 to N
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter N: ");
    scanf("%d", &n);
    int a[n-1];
    printf("Enter %d elements (from 1 to %d, missing one): ", n-1, n);
    for (int i = 0; i < n-1; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    int total = n * (n+1) / 2;
    printf("Missing number = %d\n", total - sum);
    return 0;
}
```
60) Find the majority element in an array (appears more than n/2 times)

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);

    int majority = -1;
    for (int i = 0; i < n; i++) {
        int count = 0;
        for (int j = 0; j < n; j++) {
            if (a[i] == a[j]) count++;
        }
        if (count > n/2) {
            majority = a[i];
            break;
        }
    }

    if (majority != -1) printf("Majority element = %d\n", majority);
    else printf("No majority element\n");
    return 0;
}
```
61) Print a star pattern using nested loops
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }
    return 0;
}
```
62) Linear search in an array
```
#include <stdio.h>
int main() {
    int n, key, found = 0;
    printf("Enter size: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &a[i]);
    printf("Enter element to search: ");
    scanf("%d", &key);

    for (int i = 0; i < n; i++) {
        if (a[i] == key) {
            printf("Element found at index %d\n", i);
            found = 1;
            break;
        }
    }

    if (!found) printf("Element not found\n");
    return 0;
}
```
63) Check whether a number is palindrome in decimal and binary
```
#include <stdio.h>

// Function to check palindrome
int isPalindrome(int num) {
    int rev = 0, temp = num;
    while (temp > 0) {
        rev = rev * 10 + temp % 10;
        temp /= 10;
    }
    return rev == num;
}

// Function to check binary palindrome
int isBinaryPalindrome(int num) {
    int bin[32], k = 0;
    while (num > 0) {
        bin[k++] = num % 2;
        num /= 2;
    }
    for (int i = 0; i < k/2; i++) {
        if (bin[i] != bin[k-1-i]) return 0;
    }
    return 1;
}

int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);

    if (isPalindrome(n)) printf("Decimal Palindrome\n");
    else printf("Not Decimal Palindrome\n");

    if (isBinaryPalindrome(n)) printf("Binary Palindrome\n");
    else printf("Not Binary Palindrome\n");

    return 0;
}
```
64) Sum of first N natural numbers not divisible by 3 or 5
```
#include <stdio.h>
int main() {
    int n, sum = 0, count = 0, i = 1;
    printf("Enter N: ");
    scanf("%d", &n);

    while (count < n) {
        if (i % 3 != 0 && i % 5 != 0) {
            sum += i;
            count++;
        }
        i++;
    }

    printf("Sum = %d\n", sum);
    return 0;
}
```
65) Sum of even numbers between two numbers
```
#include <stdio.h>
int main() {
    int a, b, sum = 0;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    for (int i = a; i <= b; i++) {
        if (i % 2 == 0) sum += i;
    }

    printf("Sum of even numbers = %d\n", sum);
    return 0;
}
```
66) Sum of odd numbers between two numbers
```
#include <stdio.h>
int main() {
    int a, b, sum = 0;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    for (int i = a; i <= b; i++) {
        if (i % 2 != 0) sum += i;
    }

    printf("Sum of odd numbers = %d\n", sum);
    return 0;
}
```
67) Check whether a number is a perfect square
```
#include <stdio.h>
int main() {
    int n, flag = 0;
    printf("Enter number: ");
    scanf("%d", &n);

    for (int i = 1; i*i <= n; i++) {
        if (i*i == n) {
            flag = 1;
            break;
        }
    }

    if (flag) printf("Perfect square\n");
    else printf("Not a perfect square\n");
    return 0;
}
```
68) Calculate power of a number
```
#include <stdio.h>
int main() {
    int base, exp, result = 1;
    printf("Enter base and exponent: ");
    scanf("%d %d", &base, &exp);

    for (int i = 0; i < exp; i++) result *= base;

    printf("%d^%d = %d\n", base, exp, result);
    return 0;
}
```
69) Find ASCII value of a character
```
#include <stdio.h>
int main() {
    char c;
    printf("Enter a character: ");
    scanf(" %c", &c);
    printf("ASCII value of %c = %d\n", c, c);
    return 0;
}
```
70) Find area of a circle
```
#include <stdio.h>
int main() {
    float r, area;
    printf("Enter radius: ");
    scanf("%f", &r);

    if (r >= 0) {
        area = 3.14159 * r * r;
        printf("Area = %.2f\n", area);
    } else {
        printf("Invalid radius\n");
    }
    return 0;
}
```
71) Sum of all prime numbers between 1 and 1000
```
#include <stdio.h>
int main() {
    int sum = 0;
    for (int i = 2; i <= 1000; i++) {
        int prime = 1;
        for (int j = 2; j*j <= i; j++) {
            if (i % j == 0) {
                prime = 0;
                break;
            }
        }
        if (prime) sum += i;
    }
    printf("Sum of primes between 1 and 1000 = %d\n", sum);
    return 0;
}
```
72) Print hollow square star pattern
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n; j++) {
            if (i == 1 || i == n || j == 1 || j == n)
                printf("* ");
            else
                printf("  ");
        }
        printf("\n");
    }
    return 0;
}
```
73) Print right triangle star pattern
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) printf("* ");
        printf("\n");
    }
    return 0;
}
```
74) Print mirrored right triangle star pattern
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n-i; j++) printf("  ");
        for (int j = 1; j <= i; j++) printf("* ");
        printf("\n");
    }
    return 0;
}
```
75) Print pyramid star pattern
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n-i; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) printf("*");
        printf("\n");
    }
    return 0;
}
```
76) Print mirrored pyramid star pattern (inverted)
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = n; i >= 1; i--) {
        for (int j = 1; j <= n-i; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) printf("*");
        printf("\n");
    }
    return 0;
}
```
77) Print diamond star pattern

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) printf("*");
        printf("\n");
    }
    for (int i = n-1; i >= 1; i--) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) printf("*");
        printf("\n");
    }
    return 0;
}
```
78) Print hollow diamond star pattern
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) {
            if (j == 1 || j == 2*i-1) printf("*");
            else printf(" ");
        }
        printf("\n");
    }
    for (int i = n-1; i >= 1; i--) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= 2*i-1; j++) {
            if (j == 1 || j == 2*i-1) printf("*");
            else printf(" ");
        }
        printf("\n");
    }
    return 0;
}
```
79) Print pyramid of numbers
```
#include <stdio.h>
int main() {
    int n, k = 1;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= i; j++) printf("%d ", k++);
        printf("\n");
    }
    return 0;
}
```
80) Print mirrored pyramid of numbers
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= i; j++) printf("%d ", j);
        printf("\n");
    }
    return 0;
}
```
81) Print right triangle of numbers
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= i; j++) printf("%d ", j);
        printf("\n");
    }
    return 0;
}
```
82) Print mirrored right triangle of numbers
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n-i; j++) printf("  ");
        for (int j = 1; j <= i; j++) printf("%d ", j);
        printf("\n");
    }
    return 0;
}
```
83) Print pyramid of alphabets
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    char ch = 'A';
    for (int i = 1; i <= n; i++) {
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= i; j++) printf("%c ", ch++);
        printf("\n");
    }
    return 0;
}
```
84) Print mirrored pyramid of alphabets
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        char ch = 'A';
        for (int j = i; j < n; j++) printf(" ");
        for (int j = 1; j <= i; j++) printf("%c ", ch++);
        printf("\n");
    }
    return 0;
}
```
85) Print right triangle of alphabets
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter rows: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        char ch = 'A';
        for (int j = 1; j <= i; j++) printf("%c ", ch++);
        printf("\n");
    }
    return 0;
}
```
86) Find area of a rectangle
```
#include <stdio.h>
int main() {
    float l, b, area;
    printf("Enter length and breadth: ");
    scanf("%f %f", &l, &b);

    if (l > 0 && b > 0) {
        area = l * b;
        printf("Area = %.2f\n", area);
    } else {
        printf("Invalid dimensions\n");
    }
    return 0;
}
```
87) Sum of cubes of digits of a number
```
#include <stdio.h>
int main() {
    int n, sum = 0, d;
    printf("Enter number: ");
    scanf("%d", &n);

    int temp = n;
    while (temp > 0) {
        d = temp % 10;
        sum += d*d*d;
        temp /= 10;
    }

    printf("Sum of cubes of digits = %d\n", sum);
    return 0;
}
```
88) Sum of even and odd digits separately

```
#include <stdio.h>
int main() {
    int n, d, even = 0, odd = 0;
    printf("Enter number: ");
    scanf("%d", &n);

    while (n > 0) {
        d = n % 10;
        if (d % 2 == 0) even += d;
        else odd += d;
        n /= 10;
    }

    printf("Sum of even digits = %d\n", even);
    printf("Sum of odd digits = %d\n", odd);
    return 0;
}
```
