# C Program to Represent a 2D Point and Check Equality

```c
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

    printf("Enter coordinates of first point (x y): ");
    scanf("%d %d", &p1.x, &p1.y);

    printf("Enter coordinates of second point (x y): ");
    scanf("%d %d", &p2.x, &p2.y);

    if (arePointsEqual(p1, p2)) {
        printf("The points are equal.\n");
    } else {
        printf("The points are not equal.\n");
    }

    return 0;
}


```
