# C Program to Represent a Shape Using a Union and Calculate Areas

```c
#include <stdio.h>

union Shape {
    float radius;            // for circle
    struct {
        float length;
        float breadth;
    } rectangle;
    struct {
        float base;
        float height;
    } triangle;
};

enum ShapeType { CIRCLE, RECTANGLE, TRIANGLE };

float area(union Shape s, enum ShapeType type) {
    switch (type) {
        case CIRCLE:
            return 3.14159 * s.radius * s.radius;
        case RECTANGLE:
            return s.rectangle.length * s.rectangle.breadth;
        case TRIANGLE:
            return 0.5 * s.triangle.base * s.triangle.height;
        default:
            return 0;
    }
}

int main() {
    union Shape s;
    enum ShapeType type;

    printf("Select shape (0: Circle, 1: Rectangle, 2: Triangle): ");
    int choice;
    scanf("%d", &choice);
    type = choice;

    switch (type) {
        case CIRCLE:
            printf("Enter radius of circle: ");
            scanf("%f", &s.radius);
            break;
        case RECTANGLE:
            printf("Enter length and breadth of rectangle: ");
            scanf("%f %f", &s.rectangle.length, &s.rectangle.breadth);
            break;
        case TRIANGLE:
            printf("Enter base and height of triangle: ");
            scanf("%f %f", &s.triangle.base, &s.triangle.height);
            break;
        default:
            printf("Invalid shape.\n");
            return 1;
    }

    printf("Area: %.2f\n", area(s, type));

    return 0;
}
```
