1) Store elements in an array and print them

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i+1);
        scanf("%d", &arr[i]);
    }

    printf("Array elements: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```
2) Read n numbers and display them in reverse order
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Reverse order: ");
    for (int i = n-1; i >= 0; i--) printf("%d ", arr[i]);
    return 0;
}
```
3) Find the sum of all elements of an array
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }

    printf("Sum = %d\n", sum);
    return 0;
}
```
4) Copy elements of one array into another
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr1[n], arr2[n];
    for (int i = 0; i < n; i++) scanf("%d", &arr1[i]);
    for (int i = 0; i < n; i++) arr2[i] = arr1[i];

    printf("Copied array: ");
    for (int i = 0; i < n; i++) printf("%d ", arr2[i]);
    return 0;
}
```
5) Count total number of duplicate elements in an array
```
#include <stdio.h>
int main() {
    int n, count = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (int i = 0; i < n; i++) {
        for (int j = i+1; j < n; j++) {
            if (arr[i] == arr[j]) {
                count++;
                break;
            }
        }
    }

    printf("Total duplicate elements = %d\n", count);
    return 0;
}
```
6) Print all unique elements in an array
```
#include <stdio.h>
int main() {
    int n, isUnique;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Unique elements: ");
    for (int i = 0; i < n; i++) {
        isUnique = 1;
        for (int j = 0; j < n; j++) {
            if (i != j && arr[i] == arr[j]) {
                isUnique = 0;
                break;
            }
        }
        if (isUnique) printf("%d ", arr[i]);
    }
    return 0;
}
```
7) Merge two arrays and sort in descending order
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of arrays: ");
    scanf("%d", &n);

    int arr1[n], arr2[n], merged[2*n];
    for (int i = 0; i < n; i++) scanf("%d", &arr1[i]);
    for (int i = 0; i < n; i++) scanf("%d", &arr2[i]);

    for (int i = 0; i < n; i++) merged[i] = arr1[i];
    for (int i = 0; i < n; i++) merged[n+i] = arr2[i];

    for (int i = 0; i < 2*n-1; i++) {
        for (int j = i+1; j < 2*n; j++) {
            if (merged[i] < merged[j]) {
                int temp = merged[i];
                merged[i] = merged[j];
                merged[j] = temp;
            }
        }
    }

    printf("Merged array in descending order: ");
    for (int i = 0; i < 2*n; i++) printf("%d ", merged[i]);
    return 0;
}
```
8) Count frequency of each element in an array
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n], freq[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        freq[i] = -1;
    }

    for (int i = 0; i < n; i++) {
        if (freq[i] == -1) {
            int count = 1;
            for (int j = i+1; j < n; j++) {
                if (arr[i] == arr[j]) {
                    count++;
                    freq[j] = 0;
                }
            }
            freq[i] = count;
        }
    }

    printf("Frequency of elements:\n");
    for (int i = 0; i < n; i++) {
        if (freq[i] != 0) printf("%d occurs %d times\n", arr[i], freq[i]);
    }
    return 0;
}
```
9) Find maximum and minimum element in an array
```
#include <stdio.h>
int main() {
    int n, max, min;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    max = min = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) max = arr[i];
        if (arr[i] < min) min = arr[i];
    }

    printf("Max = %d, Min = %d\n", max, min);
    return 0;
}
```
10) Separate odd and even integers into two arrays
```
#include <stdio.h>
int main() {
    int n, even[50], odd[50], e = 0, o = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        if (arr[i] % 2 == 0) even[e++] = arr[i];
        else odd[o++] = arr[i];
    }

    printf("Even elements: ");
    for (int i = 0; i < e; i++) printf("%d ", even[i]);

    printf("\nOdd elements: ");
    for (int i = 0; i < o; i++) printf("%d ", odd[i]);

    return 0;
}
```
11) Sort elements of an array in ascending order

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int arr[n];

    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (int i = 0; i < n-1; i++) {
        for (int j = i+1; j < n; j++) {
            if (arr[i] > arr[j]) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }

    printf("Sorted array in ascending order: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
12) Sort elements of an array in descending order
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int arr[n];

    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (int i = 0; i < n-1; i++) {
        for (int j = i+1; j < n; j++) {
            if (arr[i] < arr[j]) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
    }

    printf("Sorted array in descending order: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
13) Delete an element at a desired position from an array
```
#include <stdio.h>
int main() {
    int n, pos;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int arr[n];

    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Enter position to delete (1-%d): ", n);
    scanf("%d", &pos);

    if (pos < 1 || pos > n) {
        printf("Invalid position!");
    } else {
        for (int i = pos-1; i < n-1; i++) arr[i] = arr[i+1];
        n--;
        printf("Array after deletion: ");
        for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    }
    return 0;
}
```
14) Find the second largest element in an array
```
#include <stdio.h>
int main() {
    int n, first, second;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int arr[n];

    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    first = second = -1e9;
    for (int i = 0; i < n; i++) {
        if (arr[i] > first) {
            second = first;
            first = arr[i];
        } else if (arr[i] > second && arr[i] != first) {
            second = arr[i];
        }
    }

    printf("Second largest element = %d\n", second);
    return 0;
}
```
15) Find the second smallest element in an array
```
#include <stdio.h>
int main() {
    int n, first, second;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int arr[n];

    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    first = second = 1e9;
    for (int i = 0; i < n; i++) {
        if (arr[i] < first) {
            second = first;
            first = arr[i];
        } else if (arr[i] < second && arr[i] != first) {
            second = arr[i];
        }
    }

    printf("Second smallest element = %d\n", second);
    return 0;
}
```
16) 2D array of size 3x3 and print the matrix
```
#include <stdio.h>
int main() {
    int arr[3][3];
    printf("Enter 3x3 matrix:\n");

    for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
            scanf("%d", &arr[i][j]);

    printf("Matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++)
            printf("%d ", arr[i][j]);
        printf("\n");
    }
    return 0;
}
```
17) Add two matrices of same size
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

    printf("Sum matrix:\n");
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
18) Subtract two matrices
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c], b[r][c], sub[r][c];

    printf("Enter first matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    printf("Enter second matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &b[i][j]);

    printf("Subtraction matrix:\n");
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            sub[i][j] = a[i][j] - b[i][j];
            printf("%d ", sub[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```
19) Multiply two square matrices
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of square matrices: ");
    scanf("%d", &n);
    int a[n][n], b[n][n], mul[n][n];

    printf("Enter first matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    printf("Enter second matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &b[i][j]);

    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++) {
            mul[i][j] = 0;
            for (int k = 0; k < n; k++)
                mul[i][j] += a[i][k] * b[k][j];
        }

    printf("Multiplication matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++)
            printf("%d ", mul[i][j]);
        printf("\n");
    }
    return 0;
}
```
20) Find transpose of a given matrix
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int a[r][c], trans[c][r];

    printf("Enter matrix:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            trans[j][i] = a[i][j];

    printf("Transpose:\n");
    for (int i = 0; i < c; i++) {
        for (int j = 0; j < r; j++)
            printf("%d ", trans[i][j]);
        printf("\n");
    }
    return 0;
}
```
21) Find sum of right diagonals of a matrix
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter size of square matrix: ");
    scanf("%d", &n);
    int a[n][n];

    printf("Enter matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    for (int i = 0; i < n; i++) sum += a[i][i];

    printf("Sum of right diagonal = %d\n", sum);
    return 0;
}
```
22) Find sum of left diagonals of a matrix
```
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter size of square matrix: ");
    scanf("%d", &n);
    int a[n][n];

    printf("Enter matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    for (int i = 0; i < n; i++) sum += a[i][n-1-i];

    printf("Sum of left diagonal = %d\n", sum);
    return 0;
}
```
23) Find sum of rows and columns of a matrix
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
        int rowSum = 0;
        for (int j = 0; j < c; j++) rowSum += a[i][j];
        printf("Row %d sum = %d\n", i+1, rowSum);
    }

    for (int j = 0; j < c; j++) {
        int colSum = 0;
        for (int i = 0; i < r; i++) colSum += a[i][j];
        printf("Column %d sum = %d\n", j+1, colSum);
    }
    return 0;
}
```
24) Print/display lower triangular of a matrix
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of square matrix: ");
    scanf("%d", &n);
    int a[n][n];

    printf("Enter matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    printf("Lower triangular matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (i >= j) printf("%d ", a[i][j]);
            else printf("0 ");
        }
        printf("\n");
    }
    return 0;
}
```
25) Print/display upper triangular of a matrix
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size of square matrix: ");
    scanf("%d", &n);
    int a[n][n];

    printf("Enter matrix:\n");
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    printf("Upper triangular matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            if (i <= j) printf("%d ", a[i][j]);
            else printf("0 ");
        }
        printf("\n");
    }
    return 0;
}
```
26) Calculate determinant of a 3x3 matrix
```
#include <stdio.h>
int main() {
    int a[3][3];
    printf("Enter 3x3 matrix:\n");
    for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
            scanf("%d", &a[i][j]);

    int det = a[0][0]*(a[1][1]*a[2][2]-a[1][2]*a[2][1])
            - a[0][1]*(a[1][0]*a[2][2]-a[1][2]*a[2][0])
            + a[0][2]*(a[1][0]*a[2][1]-a[1][1]*a[2][0]);

    printf("Determinant = %d\n", det);
    return 0;
}
```
27. Write a program in C to accept two matrices and check whether they are equal.
```
#include <stdio.h>
int main() {
    int r, c, i, j, equal = 1;
    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &c);

    int a[r][c], b[r][c];
    printf("Enter elements of first matrix:\n");
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    printf("Enter elements of second matrix:\n");
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            scanf("%d", &b[i][j]);

    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            if (a[i][j] != b[i][j]) equal = 0;

    if (equal) printf("Matrices are equal\n");
    else printf("Matrices are not equal\n");
    return 0;
}
```
28. Write a program in C to find the majority element of an array.
```
#include <stdio.h>
int main() {
    int n, i, j, count, maxCount = 0, majority = -1;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (i = 0; i < n; i++) {
        count = 0;
        for (j = 0; j < n; j++)
            if (arr[j] == arr[i]) count++;
        if (count > maxCount) {
            maxCount = count;
            majority = arr[i];
        }
    }
    if (maxCount > n / 2)
        printf("Majority Element = %d\n", majority);
    else
        printf("No Majority Element\n");
    return 0;
}
```
29. Write a program in C to find the missing number in a given array.
```
#include <stdio.h>
int main() {
    int n, i, sum = 0, total;
    printf("Enter n: ");
    scanf("%d", &n);
    int arr[n - 1];
    printf("Enter %d numbers (from 1 to %d with one missing):\n", n - 1, n);
    for (i = 0; i < n - 1; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    total = n * (n + 1) / 2;
    printf("Missing Number = %d\n", total - sum);
    return 0;
}
```
30. Write a program in C to find the two repeating elements in a given array.
```
#include <stdio.h>
int main() {
    int n, i, j;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements:\n");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Repeating elements: ");
    for (i = 0; i < n; i++)
        for (j = i + 1; j < n; j++)
            if (arr[i] == arr[j]) {
                printf("%d ", arr[i]);
                break;
            }
    return 0;
}
```
31. Write a program to check if a given element is present in an array.
```
#include <stdio.h>
int main() {
    int n, i, key, found = 0;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Enter element to search: ");
    scanf("%d", &key);

    for (i = 0; i < n; i++)
        if (arr[i] == key) { found = 1; break; }

    if (found) printf("%d found at position %d\n", key, i + 1);
    else printf("Not found\n");
    return 0;
}
```
32. Create a function to calculate the average of elements in an array.
```
#include <stdio.h>
float average(int arr[], int n) {
    int i, sum = 0;
    for (i = 0; i < n; i++) sum += arr[i];
    return (float)sum / n;
}
int main() {
    int n, i;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);
    printf("Average = %.2f\n", average(arr, n));
    return 0;
}
```
33. Write a program to count the number of even and odd elements in an array.
```
#include <stdio.h>
int main() {
    int n, i, even = 0, odd = 0;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        if (arr[i] % 2 == 0) even++;
        else odd++;
    }
    printf("Even = %d, Odd = %d\n", even, odd);
    return 0;
}
```
34. Implement a function to reverse the elements of an array.
```
#include <stdio.h>
void reverse(int arr[], int n) {
    int i, temp;
    for (i = 0; i < n / 2; i++) {
        temp = arr[i];
        arr[i] = arr[n - i - 1];
        arr[n - i - 1] = temp;
    }
}
int main() {
    int n, i;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);

    reverse(arr, n);
    printf("Reversed array: ");
    for (i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
35. Implement a function to delete an element at a specific position in an array.
```
#include <stdio.h>
int main() {
    int n, i, pos;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Enter position to delete (1-%d): ", n);
    scanf("%d", &pos);

    if (pos < 1 || pos > n) printf("Invalid position\n");
    else {
        for (i = pos - 1; i < n - 1; i++)
            arr[i] = arr[i + 1];
        n--;
        printf("Array after deletion: ");
        for (i = 0; i < n; i++) printf("%d ", arr[i]);
    }
    return 0;
}
```
36. Write a function to find the product of all elements in an array.
```
#include <stdio.h>
long long product(int arr[], int n) {
    long long prod = 1;
    for (int i = 0; i < n; i++)
        prod *= arr[i];
    return prod;
}
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Product = %lld\n", product(arr, n));
    return 0;
}
```
37. Print Square of Array Elements in C
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Squares: ");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i] * arr[i]);
    return 0;
}
```
38. Print ASCII Values using Array in C
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    printf("ASCII Values:\n");
    for (int i = 0; str[i] != '\0'; i++)
        printf("%c = %d\n", str[i], str[i]);
    return 0;
}
```
39. C Program To Find Two Elements whose Sum is Closest to Zero
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    int minSum = __INT_MAX__, a = 0, b = 0;
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            int sum = arr[i] + arr[j];
            if (abs(sum) < abs(minSum)) {
                minSum = sum;
                a = arr[i];
                b = arr[j];
            }
        }
    }
    printf("Pair: %d and %d (Sum = %d)\n", a, b, minSum);
    return 0;
}
```
40. C Program to Find Union and Intersection of Two Arrays
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

    printf("Union: ");
    for (int i = 0; i < n1; i++) printf("%d ", a[i]);
    for (int i = 0; i < n2; i++) {
        int found = 0;
        for (int j = 0; j < n1; j++)
            if (b[i] == a[j]) { found = 1; break; }
        if (!found) printf("%d ", b[i]);
    }

    printf("\nIntersection: ");
    for (int i = 0; i < n1; i++)
        for (int j = 0; j < n2; j++)
            if (a[i] == b[j]) printf("%d ", a[i]);
    return 0;
}
```
41. C Program to Print all Non-Repeated Elements in an Array
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Non-repeated elements: ");
    for (int i = 0; i < n; i++) {
        int count = 0;
        for (int j = 0; j < n; j++)
            if (arr[i] == arr[j]) count++;
        if (count == 1) printf("%d ", arr[i]);
    }
    return 0;
}
```
42. Write a program to write all the elements of 2-D Array into 1-D Array in row wise.
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int arr[r][c], oneD[r * c], k = 0;

    printf("Enter elements:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &arr[i][j]);

    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            oneD[k++] = arr[i][j];

    printf("1D Array: ");
    for (int i = 0; i < r * c; i++) printf("%d ", oneD[i]);
    return 0;
}
```
43. Write a program to print a rectangular matrix spirally
```
#include <stdio.h>
int main() {
    int r, c;
    printf("Enter rows and cols: ");
    scanf("%d %d", &r, &c);
    int arr[r][c];
    printf("Enter elements:\n");
    for (int i = 0; i < r; i++)
        for (int j = 0; j < c; j++)
            scanf("%d", &arr[i][j]);

    int top = 0, bottom = r - 1, left = 0, right = c - 1;
    printf("Spiral order: ");
    while (top <= bottom && left <= right) {
        for (int i = left; i <= right; i++) printf("%d ", arr[top][i]);
        top++;
        for (int i = top; i <= bottom; i++) printf("%d ", arr[i][right]);
        right--;
        if (top <= bottom) {
            for (int i = right; i >= left; i--) printf("%d ", arr[bottom][i]);
            bottom--;
        }
        if (left <= right) {
            for (int i = bottom; i >= top; i--) printf("%d ", arr[i][left]);
            left++;
        }
    }
    return 0;
}
```
44. Write a program to print Spiral Matrix (n × n, filled with 1 to n²)
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter n: ");
    scanf("%d", &n);
    int arr[n][n];

    int top = 0, bottom = n - 1, left = 0, right = n - 1, num = 1;
    while (top <= bottom && left <= right) {
        for (int i = left; i <= right; i++) arr[top][i] = num++;
        top++;
        for (int i = top; i <= bottom; i++) arr[i][right] = num++;
        right--;
        for (int i = right; i >= left; i--) arr[bottom][i] = num++;
        bottom--;
        for (int i = bottom; i >= top; i--) arr[i][left] = num++;
        left++;
    }

    printf("Spiral Matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) printf("%3d ", arr[i][j]);
        printf("\n");
    }
    return 0;
}
```
45. Write a program to partition an array such that all negatives on left and positives on right
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    int left = 0, right = n - 1;
    while (left <= right) {
        if (arr[left] < 0) left++;
        else if (arr[right] >= 0) right--;
        else {
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
    }

    printf("Partitioned Array: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
46. Write a program to create next_ge[] (Next Greater Element array)
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n], next_ge[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    for (int i = 0; i < n; i++) {
        next_ge[i] = -1;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] > arr[i]) {
                next_ge[i] = arr[j];
                break;
            }
        }
    }

    printf("Next Greater Elements: ");
    for (int i = 0; i < n; i++) printf("%d ", next_ge[i]);
    return 0;
}
```
47. Write a program to find the kth smallest element in an array
```
#include <stdio.h>
void sort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++)
        for (int j = i + 1; j < n; j++)
            if (arr[i] > arr[j]) {
                int temp = arr[i]; arr[i] = arr[j]; arr[j] = temp;
            }
}
int main() {
    int n, k;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);
    printf("Enter k: ");
    scanf("%d", &k);

    sort(arr, n);
    if (k > 0 && k <= n)
        printf("%d-th Smallest = %d\n", k, arr[k - 1]);
    else
        printf("Invalid k\n");
    return 0;
}
```
48. Write a program to reverse a portion of an array
```
#include <stdio.h>
void reverse(int arr[], int l, int r) {
    while (l < r) {
        int temp = arr[l];
        arr[l] = arr[r];
        arr[r] = temp;
        l++; r--;
    }
}
int main() {
    int n, l, r;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    printf("Enter start and end indices to reverse: ");
    scanf("%d %d", &l, &r);

    reverse(arr, l, r);

    printf("Modified Array: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
49. Write a program to rotate array left by one element (first becomes last)
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);

    int first = arr[0];
    for (int i = 0; i < n - 1; i++) arr[i] = arr[i + 1];
    arr[n - 1] = first;

    printf("Rotated Array: ");
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
```
50. Write a program to rotate the array left by k elements

```

#include <stdio.h>
void rotateLeft(int arr[], int n, int k) {
    k = k % n; // handle cases where k > n
    int temp[k];
    
   
    for (int i = 0; i < k; i++)
        temp[i] = arr[i];
    
   
    for (int i = 0; i < n - k; i++)
        arr[i] = arr[i + k];
    
   
    for (int i = 0; i < k; i++)
        arr[n - k + i] = temp[i];
}

int main() {
    int n, k;
    printf("Enter size: ");
    scanf("%d", &n);
    int arr[n];
    printf("Enter elements: ");
    for (int i = 0; i < n; i++) scanf("%d", &arr[i]);
    printf("Enter k: ");
    scanf("%d", &k);

    rotateLeft(arr, n, k);

    printf("Array after rotating %d elements: ", k);
    for (int i = 0; i < n; i++) printf("%d ", arr[i]);
    return 0;
}
````
