# C Program to Validate a Date Using a Structure

```c
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int isLeapYear(int year) {
    return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
}

int isValidDate(struct Date d) {
    if (d.year < 1 || d.month < 1 || d.month > 12 || d.day < 1)
        return 0;

    int daysInMonth[] = {0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};

    if (d.month == 2 && isLeapYear(d.year))
        return d.day <= 29;

    return d.day <= daysInMonth[d.month];
}

int main() {
    struct Date d;

    printf("Enter day: ");
    scanf("%d", &d.day);
    printf("Enter month: ");
    scanf("%d", &d.month);
    printf("Enter year: ");
    scanf("%d", &d.year);

    if (isValidDate(d))
        printf("The date %02d/%02d/%d is valid.\n", d.day, d.month, d.year);
    else
        printf("The date %02d/%02d/%d is invalid.\n", d.day, d.month, d.year);

    return 0;
}
```
