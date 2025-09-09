1. What keyword is used to define a structure in C?
a) struct
b) union
c) typedef
d) define
Answer: a

2. Which of the following statements is true about accessing members of a structure?
a) Members are accessed using the dot (.) operator
b) Members are accessed using the arrow (->) operator
c) All members must have the same data type
d) Structures cannot hold members of different data types
Answer: a

3. What is the size of a structure in memory?
a) The size is always equal to the size of its largest member
b) The size is the sum of the sizes of all its members
c) The size depends on the compiler implementation
d) Structures do not occupy any memory space
Answer: c

4. What is the difference between a structure and a union?
a) Structures cannot hold different data types, while unions can
b) Unions can only hold one value at a time, while structures can hold multiple values
c) Structures are used for grouping related data, while unions are used for memory optimization
d) All of the above
Answer: b

5. Which of the following statements is NOT valid for initializing a structure?
a) Using a comma-separated list of values inside curly braces
b) Assigning another structure variable of the same type
c) Using individual assignment statements for each member
d) Initializing only some members, leaving others undefined
Answer: d

6. What is the purpose of the -> operator when accessing members of a structure?
a) It is used to access members of a structure pointer variable
b) It is used to modify members of a structure by reference
c) It is an alternative way to access members of any structure
d) It is not a valid operator for accessing structure members
Answer: a

7. How can you pass a structure by value to a function in C?
a) By passing the structure variable directly
b) By passing the structure variable using the & (address-of) operator
c) By creating a pointer to the structure and passing the pointer
d) Structures cannot be passed by value to functions
Answer: a

8. What happens when you declare an array of structures?
a) It creates a single structure variable that can hold multiple values
b) It creates multiple copies of the same structure in memory
c) It creates a contiguous block of memory to store multiple structures of the same type
d) It creates a linked list of structures
Answer: c

9. What is padding in the context of structures?
a) It is the process of adding extra bytes to the size of a structure to improve memory alignment
b) It is a technique to optimize memory usage by storing smaller data types within larger ones
c) It is a way to dynamically allocate memory for structures at runtime
d) Padding is not relevant to structures in C
Answer: a

10. What is the most common use case for unions in C programming?
a) To group related data of different types under a single name
b) To store multiple values of the same type and access them interchangeably
c) To improve code readability and maintainability
d) To dynamically change the data type of a variable during program execution
Answer: a

11. What is the difference between shallow copy and deep copy when copying structures?
a) Shallow copy copies only the structure itself, while deep copy copies the members recursively
b) Shallow copy copies the structure by value, while deep copy copies by reference
c) Shallow copy uses the = operator, while deep copy requires a custom function
d) There is no difference; both terms refer to the same process
Answer: a

12. What is the use of self-referential structures in C?
a) To represent hierarchical relationships between data, like a tree structure
b) To create circular references that can lead to memory leaks
c) To improve code efficiency by avoiding redundant member declarations
d) Self-referential structures are not allowed in C
Answer: a

13. What are bit fields in C?
a) A way to pack multiple small data types (like flags) into a single byte of memory
b) A mechanism to define custom operators for user-defined data types
c) A technique to dynamically allocate memory for structures during runtime
d) Bit fields are not relevant to structures in C
Answer: a

14. How can you compare two structures for equality in C?
a) By comparing the addresses of the structure variables
b) By using a built-in compare function for structures
c) By writing a custom function that compares each member individually
d) Structures cannot be compared for equality
Answer: c

15. What is the potential consequence of accessing a union member that hasn’t been initialized?
a) The program will crash due to undefined behavior
b) The value accessed will be the same as the previously accessed member
c) The value accessed will be garbage or random data
d) There is no consequence; any member can be accessed regardless of initialization
Answer: c

16. What is the use of anonymous structures in C?
a) To declare a structure without a name, used only once within a function
b) To define a structure template that can be used to create multiple instances with different names
c) To create a structure that cannot be accessed directly and must be used through a pointer
d) Anonymous structures are not supported in C
Answer: a

17. How can you define a structure within another structure in C?
a) By using nested structures, where one structure is a member of another
b) By creating a pointer to the inner structure within the outer structure
c) By defining both structures separately and using them independently
d) Structures cannot be members of other structures in C
Answer: a

18. Create a structure to represent a student and display details

```
#include <stdio.h>

struct Student {
    char name[50];
    int roll_no;
    float marks;
};

void displayStudent(struct Student s) {
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll_no);
    printf("Marks: %.2f\n", s.marks);
}

int main() {
    struct Student s1;

    printf("Enter name: ");
    scanf("%s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll_no);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    printf("\nStudent Details:\n");
    displayStudent(s1);

    return 0;
}
```
19. Define a union to store either an integer or a float

```
#include <stdio.h>

union Data {
    int i;
    float f;
};

void readAndPrintUnion() {
    union Data d;
    int choice;

    printf("Enter 1 for integer, 2 for float: ");
    scanf("%d", &choice);

    if (choice == 1) {
        printf("Enter an integer: ");
        scanf("%d", &d.i);
        printf("Stored integer: %d\n", d.i);
    } else if (choice == 2) {
        printf("Enter a float: ");
        scanf("%f", &d.f);
        printf("Stored float: %.2f\n", d.f);
    } else {
        printf("Invalid choice!\n");
    }
}

int main() {
    readAndPrintUnion();
    return 0;
}
```
20. Define a structure for a 2D point and check equality
```
#include <stdio.h>

struct Point {
    int x;
    int y;
};

int arePointsEqual(struct Point p1, struct Point p2) {
    return (p1.x == p2.x && p1.y == p2.y);
}

int main() {
    struct Point p1, p2;

    printf("Enter coordinates for Point 1 (x y): ");
    scanf("%d %d", &p1.x, &p1.y);

    printf("Enter coordinates for Point 2 (x y): ");
    scanf("%d %d", &p2.x, &p2.y);

    if (arePointsEqual(p1, p2)) {
        printf("Points are equal.\n");
    } else {
        printf("Points are not equal.\n");
    }

    return 0;
}
```
21. Structure to represent a book and accept details from user
```
#include <stdio.h>

struct Book {
    char title[50];
    char author[50];
    long int ISBN;
    int pages;
};

void inputBook(struct Book *b) {
    printf("Enter title: ");
    scanf(" %[^\n]", b->title);
    printf("Enter author: ");
    scanf(" %[^\n]", b->author);
    printf("Enter ISBN: ");
    scanf("%ld", &b->ISBN);
    printf("Enter number of pages: ");
    scanf("%d", &b->pages);
}

int main() {
    struct Book myBook;
    inputBook(&myBook);

    printf("\nBook Details:\n");
    printf("Title: %s\nAuthor: %s\nISBN: %ld\nPages: %d\n",
           myBook.title, myBook.author, myBook.ISBN, myBook.pages);

    return 0;
}
```

22. Union to represent size of a product and conversion
```
#include <stdio.h>

union Size {
    float cm;
    float inch;
    float feet;
};

void cmToInch(union Size *s) {
    s->inch = s->cm / 2.54;
}

int main() {
    union Size s;
    printf("Enter size in cm: ");
    scanf("%f", &s.cm);

    cmToInch(&s);
    printf("Size in inches: %.2f\n", s.inch);
    return 0;
}

```
23. Structure for date and check leap year
```
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int isLeapYear(struct Date d) {
    int y = d.year;
    return (y % 4 == 0 && (y % 100 != 0 || y % 400 == 0));
}

int main() {
    struct Date d;
    printf("Enter year: ");
    scanf("%d", &d.year);

    if (isLeapYear(d))
        printf("%d is a leap year\n", d.year);
    else
        printf("%d is not a leap year\n", d.year);

    return 0;
}

```
24. Structure for complex number and addition
```
#include <stdio.h>

struct Complex {
    float real;
    float imag;
};

struct Complex addComplex(struct Complex c1, struct Complex c2) {
    struct Complex sum;
    sum.real = c1.real + c2.real;
    sum.imag = c1.imag + c2.imag;
    return sum;
}

int main() {
    struct Complex a, b, result;

    printf("Enter real and imaginary part of first complex number: ");
    scanf("%f %f", &a.real, &a.imag);
    printf("Enter real and imaginary part of second complex number: ");
    scanf("%f %f", &b.real, &b.imag);

    result = addComplex(a, b);
    printf("Sum = %.2f + %.2fi\n", result.real, result.imag);
    return 0;
}

```
25. Implement a linked list using structures
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

int main() {
    struct Node *head = NULL, *second, *third;

    // Allocate nodes
    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    // Assign values
    head->data = 10; head->next = second;
    second->data = 20; second->next = third;
    third->data = 30; third->next = NULL;

    // Print list
    struct Node *ptr = head;
    while (ptr != NULL) {
        printf("%d -> ", ptr->data);
        ptr = ptr->next;
    }
    printf("NULL\n");

    return 0;
}

```
26. Self-referential structure for a binary tree node
```
#include <stdio.h>
#include <stdlib.h>

struct TreeNode {
    int data;
    struct TreeNode *left;
    struct TreeNode *right;
};

int main() {
    struct TreeNode *root = (struct TreeNode*)malloc(sizeof(struct TreeNode));
    root->data = 10;
    root->left = root->right = NULL;

    printf("Root data: %d\n", root->data);
    return 0;
}

```
27. Read student data from a file and store in array of structures
```
#include <stdio.h>

struct Student {
    char name[50];
    int roll;
    float marks;
};

int main() {
    struct Student students[100];
    FILE *fp = fopen("students.txt", "r");
    int i = 0;

    if (fp == NULL) {
        printf("File not found.\n");
        return 1;
    }

    while (fscanf(fp, "%s %d %f", students[i].name, &students[i].roll, &students[i].marks) != EOF) {
        i++;
    }
    fclose(fp);

    for (int j = 0; j < i; j++) {
        printf("%s %d %.2f\n", students[j].name, students[j].roll, students[j].marks);
    }

    return 0;
}

```
28. Function to check if a date is valid
```
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int isValidDate(struct Date d) {
    int maxDays[] = {0,31,28,31,30,31,30,31,31,30,31,30,31};
    if ((d.year % 4 == 0 && d.year % 100 != 0) || (d.year % 400 == 0))
        maxDays[2] = 29;

    return (d.month >= 1 && d.month <= 12 && d.day >= 1 && d.day <= maxDays[d.month]);
}

int main() {
    struct Date d;
    printf("Enter day month year: ");
    scanf("%d %d %d", &d.day, &d.month, &d.year);

    if (isValidDate(d))
        printf("Valid date\n");
    else
        printf("Invalid date\n");

    return 0;
}

```
29. Union to represent different shapes and calculate area
```
#include <stdio.h>
#include <math.h>

union Shape {
    float radius;          
    struct {
  float l,b;
  } rectangle;
    struct { float b,h; } triangle;
};

float circleArea(float r) { return M_PI*r*r; }
float rectangleArea(float l, float b) { return l*b; }
float triangleArea(float b, float h) { return 0.5*b*h; }

int main() {
    union Shape s;
    int choice;
    printf("Choose shape: 1.Circle 2.Rectangle 3.Triangle: ");
    scanf("%d", &choice);

    switch(choice) {
        case 1:
            printf("Enter radius: "); scanf("%f", &s.radius);
            printf("Area = %.2f\n", circleArea(s.radius)); break;
        case 2:
            printf("Enter length and breadth: "); scanf("%f %f", &s.rectangle.l, &s.rectangle.b);
            printf("Area = %.2f\n", rectangleArea(s.rectangle.l, s.rectangle.b)); break;
        case 3:
            printf("Enter base and height: "); scanf("%f %f", &s.triangle.b, &s.triangle.h);
            printf("Area = %.2f\n", triangleArea(s.triangle.b, s.triangle.h)); break;
        default: printf("Invalid choice\n");
    }
    return 0;
}
```
30. Structure for playing card and generate random card
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

enum Suit {Hearts, Diamonds, Clubs, Spades};

struct Card {
    enum Suit suit;
    int rank;
};

struct Card generateCard() {
    struct Card c;
    c.suit = rand() % 4;
    c.rank = rand() % 13 + 1;
    return c;
}

void printCard(struct Card c) {
    char *suits[] = {"Hearts","Diamonds","Clubs","Spades"};
    printf("Card: %d of %s\n", c.rank, suits[c.suit]);
}

int main() {
    srand(time(0));
    struct Card c = generateCard();
    printCard(c);
    return 0;
}

```
31. Structure for time and add two durations
```
#include <stdio.h>

struct Time {
    int hours;
    int minutes;
    int seconds;
};

struct Time addTime(struct Time t1, struct Time t2) {
    struct Time sum;
    sum.seconds = t1.seconds + t2.seconds;
    sum.minutes = t1.minutes + t2.minutes + sum.seconds/60;
    sum.seconds %= 60;
    sum.hours = t1.hours + t2.hours + sum.minutes/60;
    sum.minutes %= 60;
    return sum;
}

int main() {
    struct Time t1, t2, sum;
    printf("Enter first time (h m s): "); scanf("%d %d %d", &t1.hours, &t1.minutes, &t1.seconds);
    printf("Enter second time (h m s): "); scanf("%d %d %d", &t2.hours, &t2.minutes, &t2.seconds);

    sum = addTime(t1, t2);
    printf("Sum = %d:%d:%d\n", sum.hours, sum.minutes, sum.seconds);
    return 0;
}

```
32. Student enrollment record: add and search by student ID
```
#include <stdio.h>
#include <string.h>

struct Enrollment {
    char studentID[20];
    char course[50];
    char grade;
};

void addRecord(struct Enrollment records[], int *n) {
    printf("Enter student ID: "); scanf("%s", records[*n].studentID);
    printf("Enter course name: "); scanf(" %[^\n]", records[*n].course);
    printf("Enter grade: "); scanf(" %c", &records[*n].grade);
    (*n)++;
}

int searchRecord(struct Enrollment records[], int n, char *id) {
    for(int i=0; i<n; i++) {
        if(strcmp(records[i].studentID, id) == 0) return i;
    }
    return -1;
}

int main() {
    struct Enrollment records[100];
    int n = 0, choice;
    char id[20];

    addRecord(records, &n); // Add one record for demo
    printf("Enter student ID to search: ");
    scanf("%s", id);

    int index = searchRecord(records, n, id);
    if(index != -1)
        printf("Found: %s, %s, %c\n", records[index].studentID, records[index].course, records[index].grade);
    else
        printf("Record not found\n");

    return 0;
}
```
33. Code snippet
```
struct person {
    char name[50];
    int age;
};
int main() {
    struct person p1;
    strcpy(p1.name, "John Doe");
    p1.age = 30;
    printf("Name: %s, Age: %d\n", p1.name, p1.age);
    return 0;
}


Potential Issue:

If p1.name is smaller than the string being copied, it will cause buffer overflow.

Always ensure the array is large enough for the string + null terminator.
```
34. Union printing float after assigning int
```
union data {
    int i;
    float f;
};
int main() {
    union data value;
    value.i = 10;
    printf("Float value: %f\n", value.f);
    return 0;
}


Explanation:

Union members share the same memory. Assigning i=10 and then reading f will print garbage value because the bit pattern of 10 as an int is interpreted as a float.

This is unexpected behavior; union only safely stores one value at a time.
```
35. Student marks allocated dynamically
```
struct student {
    int *marks;
    int num_subjects;
};
int main() {
    struct student s1;
    s1.num_subjects = 5;
    s1.marks = malloc(s1.num_subjects * sizeof(int));
    free(s1.marks);
    return 0;
}


Potential Issue:

If free(s1.marks) is not called, it causes a memory leak.

Dynamically allocated memory must always be freed after use.
```
36. strcpy beyond allocated memory
```
struct data {
    int i;
    char str[20];
};
void print_data(struct data *d) {
    printf("Integer: %d\n", d->i);
    printf("String: %s\n", d->str);
}


Potential Issue:

If strcpy writes beyond str[20], it causes buffer overflow, potentially corrupting memory or crashing the program.
````
37. Union modification
```
union data {
    int i;
    float f;
};
int main() {
    union data value;
    value.i = 10;
    printf("%f\n", value.f);
    value.f = 3.14;
    printf("%f\n", value.f);
    return 0;
}


Explanation:



After value.f = 3.14


38–39.
```
typedef struct {
    char A;
    int B;
    char C;
} InfoData;


Typical alignment: int aligned to 4 bytes, struct padded.

Layout: A(1) + 3 padding + B(4) + C(1) + 3 padding = 12 bytes
Size = 12
```
40.
```
typedef struct {
    double A;
    char B;
    char C;
} InfoData;


double aligned to 8 bytes.

Layout: A(8) + B(1) + C(1) + 6 padding = 16 bytes
Size = 16
```
41.
```
typedef struct {
    int A;
    int B;
    char C;
    char D;
    float E;
} InfoData;


int aligned 4 bytes, float 4 bytes.

Layout: A(4)+B(4)+C(1)+D(1)+2 padding + E(4) → 16 bytes
Size = 16
```
42.
```
typedef struct {
    char A;
    char B;
} InfoData;


Both chars: 1 byte each.

Typically 2 bytes, no padding needed.
Size = 2
```
43.
```
typedef struct {
    char A;
    short B;
    int C;
    char D;
} InfoData;


Layout: A(1)+1 padding + B(2)+C(4)+D(1)+3 padding → 12 bytes
Size = 12
```
44.
```
typedef struct {
    char A;
    double B;
    char C;
} InfoData;


Layout: A(1)+7 padding + B(8)+C(1)+7 padding → 24 bytes
Size = 24
```
45.
```
typedef struct {
    char A;
    char B;
    short C;
    int D;
} InfoData;


Layout: A(1)+B(1)+C(2)+D(4) → perfectly aligned, 8 bytes
Size = 8
```
46. Using #pragma pack(push,1)
```
#pragma pack(push, 1)
typedef struct {
    double A;
    char B;
} InfoData;
#pragma pack(pop)


1-byte packing disables padding.

Layout: double(8)+char(1) → 9 bytes
Size = 9
```
47. Using #pragma pack(push,4)
```
#pragma pack(push,4)
typedef struct {
    double A; // 8-byte
    char B;   // 1-byte
} InfoData;
#pragma pack(pop)


4-byte alignment. Layout: double(8)+char(1)+3 padding → 12 bytes
Size = 12
```
