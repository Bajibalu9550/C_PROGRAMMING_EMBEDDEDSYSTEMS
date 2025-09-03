# C Program to Represent Product Size Using a Union and Convert Units

```c
#include <stdio.h>

union Size {
    float cm;
    float inch;
    float feet;
};

void convertSize(union Size *s, char from, char to) {
    float value = 0;

    switch (from) {
        case 'c': // from centimeters
            value = s->cm;
            if (to == 'i')        // to inches
                s->inch = value / 2.54;
            else if (to == 'f')   // to feet
                s->feet = value / 30.48;
            break;

        case 'i': // from inches
            value = s->inch;
            if (to == 'c')        // to cm
                s->cm = value * 2.54;
            else if (to == 'f')   // to feet
                s->feet = value / 12;
            break;

        case 'f': // from feet
            value = s->feet;
            if (to == 'c')        // to cm
                s->cm = value * 30.48;
            else if (to == 'i')   // to inches
                s->inch = value * 12;
            break;

        default:
            printf("Invalid unit\n");
    }
}

int main() {
    union Size product;
    char fromUnit, toUnit;

    printf("Enter unit of input (c for cm, i for inches, f for feet): ");
    scanf(" %c", &fromUnit);

    printf("Enter size value: ");
    if (fromUnit == 'c')
        scanf("%f", &product.cm);
    else if (fromUnit == 'i')
        scanf("%f", &product.inch);
    else if (fromUnit == 'f')
        scanf("%f", &product.feet);

    printf("Enter unit to convert to (c for cm, i for inches, f for feet): ");
    scanf(" %c", &toUnit);

    convertSize(&product, fromUnit, toUnit);

    if (toUnit == 'c')
        printf("Converted size: %.2f cm\n", product.cm);
    else if (toUnit == 'i')
        printf("Converted size: %.2f inches\n", product.inch);
    else if (toUnit == 'f')
        printf("Converted size: %.2f feet\n", product.feet);

    return 0;
}

OUTPUT:
Enter unit of input (c for cm, i for inches, f for feet): c
Enter size value: 30
Enter unit to convert to (c for cm, i for inches, f for feet): i
Converted size: 11.81 inches

Enter unit of input (c for cm, i for inches, f for feet): f
Enter size value: 2
Enter unit to convert to (c for cm, i for inches, f for feet): c
Converted size: 60.96 cm
```
