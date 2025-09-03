# C Program to Represent a Date and Check Leap Year

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int isLeapYear(struct Date d) {
    int year = d.year;
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
        return 1;  
    else
        return 0;  
}

int main() {
    struct Date d;

    printf("Enter day: ");
    scanf("%d", &d.day);
    printf("Enter month: ");
    scanf("%d", &d.month);
    printf("Enter year: ");
    scanf("%d", &d.year);

    if (isLeapYear(d))
        printf("%d is a leap year.\n", d.year);
    else
        printf("%d is not a leap year.\n", d.year);

    return 0;
}

OUTPUT:

Enter day: 15
Enter month: 8
Enter year: 2024
2024 is a leap year.

Enter day: 1
Enter month: 1
Enter year: 2023
2023 is not a leap year.
```
