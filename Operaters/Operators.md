## 1) Which is not a bitwise operator?
1. `&`  
2. `|`  
3. `<<`  
4. `&&`  

**Answer:** `&&` (logical, not bitwise)  

---

## 2) Predict the output of the following program.
```c
#include <stdio.h>
int main()
{
}
int a=10;
int b=2;
int c;
c=(a & b);
printf("c= %d",c);
return 0;
Answer: c=2
```
3)
```
#define MOBILE  0x01
#define LAPPY   0x02
unsigned char item=0x00;
item |=MOBILE;
item |=LAPPY;
Answer: I have purchased ...: Mobile, Lappy
```
4)
```
char var=0x04;
var = var | 0x04;
printf("%d,",var);
var |= 0x01;
printf("%d",var);
Answer: 4,5
```
5)
```
char flag=0x0f;
flag &= ~0x02;
printf("%d",flag);
Answer: 13
```
6)
```
int x = 10 ^ 2;
Answer: 8
```
7)
```
int x=10;
x &= ~2;
Answer: x=8
```
8) Which Bitwise Operator can be used to check EVEN/ODD quickly?
Answer: & (Bitwise AND → (n & 1))

9) Which statement is suitable to check 3rd bit is set?
```
(num & (1<<3))

(num & 0x08)

(num & 0x03)

Both (1) and (2)

Answer: Both (1) and (2)
```

10) Left shift (<<) and Right shift (>>) operators are equivalent to _____________ by 2.
    
Answer: Multiplication and Division

12)
```
printf("value is = %d",(10++));
Answer: ERROR (cannot increment constant)
```
12)
```
const char var='A';
++var;
Answer: ERROR (cannot modify const)
```
13)
```
int x=10;
x+=(x++)+(++x)+x;
Answer: 44
```
14)
```
int a=10,b=2,x=0;
x=a+b*a+10/2*a;
Answer: value is = 80
```
15)
```
unsigned short var='B'; // 66
var+=2;   // 68
var++;    // 69
Answer: var : E, 69
```
16)
```
char var=10;
printf("var is = %d",++var++);
Answer: ERROR : L-value required
```
17)
```
int x=(20 || 40 ) && (10);
Answer: x=1
```
18)
```
x= (printf("AA")||printf("BB"));   // prints AA, x=1
x= (printf("AA")&& printf("BB"));  // prints AABB, x=1
Answer:


Copy code
AA1
AABB1
```
19)
```
int a=3,b=2;
a=a==b==0;
Answer: 1,2
```
20)
```

int intVar=20,x;
x= ++intVar,intVar++,++intVar;
Answer: Value of intVar=23, x=23
```
```
#include <stdio.h>
int main(){
 char val=250;
 int  ans;
 ans= val+ !val + ~val + ++val;
 printf("%d",ans);
 return 0;
}


Answer: -6
```

22)
```
int a = 10;
double b = 5.6;
int c;
c = a + b;
printf("%d",c);




Answer: 15
```
23)
```
int x;
x=100,30,50;
printf("x=%d\n",x);
x=(100,30,50);
printf("x=%d\n",x);



Output:

x=100
x=50
```



24)
```
int i=-1,j=-1,k=0,l=2,m;
m=i++&& j++&&k++||l++;
printf("%d %d %d %d %d",i,j,k,l,m);





Answer: 3. 0 0 1 3 1
```
25)
```
int var;
var=- -10;   // = +10
var=+ +10;   // = 10
printf("value of var= %d\n",var);
printf("value of var= %d\n",var);




Answer: 3. value of var= 10 value of var= 10
```
26)
```
int x,y;
x=(100,200);
y=100,200;
printf("x=%d,y=%d",x,y);



Output: x=200,y=100.

Answer: 4. x=200,y=100
```
27) Arrange the operators according to precedence: +, %, ->, =


Answer: 4. %, ->, =, +



## 29) How to check if a particular bit is set or not in a number?

```c
if (num & (1 << k)) {
    printf("Bit %d is SET\n", k);
} else {
    printf("Bit %d is NOT set\n", k);
}

```
30) How to represent the above all things in MACRO for Real-time code?
```
#define IS_BIT_SET(num, k)   ((num) & (1 << (k)))
#define SET_BIT(num, k)      ((num) |= (1 << (k)))
#define CLEAR_BIT(num, k)    ((num) &= ~(1 << (k)))
#define TOGGLE_BIT(num, k)   ((num) ^= (1 << (k)))
```
31) Write MACRO to Swap the bytes in 16-bit Integer Variable.
```
#define SWAP16(x)   ( ((x & 0x00FF) << 8) | ((x & 0xFF00) >> 8) )

```
32) Write MACRO to Swap the bytes in a 32-bit Integer Variable.
```
#define SWAP32(x)   ( ((x & 0x000000FF) << 24) | \
                      ((x & 0x0000FF00) << 8)  | \
                      ((x & 0x00FF0000) >> 8)  | \
                      ((x & 0xFF000000) >> 24) )

```
33) Write MACRO to Swap the bytes in a 64-bit Integer Variable.
```
#define SWAP64(x)   ( ((x & 0x00000000000000FFULL) << 56) | \
                      ((x & 0x000000000000FF00ULL) << 40) | \
                      ((x & 0x0000000000FF0000ULL) << 24) | \
                      ((x & 0x00000000FF000000ULL) << 8)  | \
                      ((x & 0x000000FF00000000ULL) >> 8)  | \
                      ((x & 0x0000FF0000000000ULL) >> 24) | \
                      ((x & 0x00FF000000000000ULL) >> 40) | \
                      ((x & 0xFF00000000000000ULL) >> 56) )
```
34) Find whether the number is odd or even
```
if (num & 1)
    printf("Odd\n");
else
    printf("Even\n");

```
35) Clear the last right side set bit of a number
```
num = num & (num - 1);
```
36) Check if the number is a power of 2
```
if (num > 0 && (num & (num - 1)) == 0)
    printf("Power of 2\n");
else
    printf("Not power of 2\n");
```
37) Count the number of set bits in a number
```
int count = 0;
while (num) {
    num &= (num - 1);  // clear last set bit
    count++;
}
printf("Set bits = %d\n", count);

```
38) Swap two bits at a given position in an integer
```
int b1 = (num >> i) & 1;
int b2 = (num >> j) & 1;
if (b1 != b2) {
    num ^= (1 << i);
    num ^= (1 << j);
}

```
39) Swap all even and odd bits
```
#define SWAP_EVEN_ODD_BITS(x) ( ((x & 0xAAAAAAAA) >> 1) | ((x & 0x55555555) << 1) )

```
40) Write a program that enters temperature in Celsius and converts that into Fahrenheit.
```
#include <stdio.h>
int main() {
    float c, f;
    printf("Enter temperature in Celsius: ");
    scanf("%f", &c);
    f = (c * 9.0 / 5.0) + 32;
    printf("Temperature in Fahrenheit: %.2f\n", f);
    return 0;
}

```
## 41) Write a program that accepts the radius of a circle and calculates the area and perimeter of that circle.

```c
#include <stdio.h>
#define PI 3.14159

int main() {
    float r, area, perimeter;
    printf("Enter radius: ");
    scanf("%f", &r);

    area = PI * r * r;
    perimeter = 2 * PI * r;

    printf("Area = %.2f\n", area);
    printf("Perimeter = %.2f\n", perimeter);
    return 0;
}
```
42) Write a program to accept a number in decimal and print the number in octal and hexadecimal.
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter decimal number: ");
    scanf("%d", &n);

    printf("Octal = %o\n", n);
    printf("Hexadecimal = %X\n", n);
    return 0;
}
```
43) Write a program to accept any number and print the value of remainder after dividing it by 3.
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);

    printf("Remainder = %d\n", n % 3);
    return 0;
}
```
44) Accept any two numbers, if the first number is greater than second then print the difference of these two numbers, otherwise print their sum. Write this program using a ternary operator.
```
#include <stdio.h>
int main() {
    int a, b, result;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    result = (a > b) ? (a - b) : (a + b);
    printf("Result = %d\n", result);
    return 0;
}
```
45) Write a program that accepts marks in five subjects and calculates the total percentage marks.
```
#include <stdio.h>
int main() {
    int m1, m2, m3, m4, m5;
    float total, percentage;

    printf("Enter marks of 5 subjects: ");
    scanf("%d %d %d %d %d", &m1, &m2, &m3, &m4, &m5);

    total = m1 + m2 + m3 + m4 + m5;
    percentage = (total / 500.0) * 100;

    printf("Total = %.2f\n", total);
    printf("Percentage = %.2f%%\n", percentage);
    return 0;
}
```
46) Can you swap two variables without using a temporary variable? Show the code.
```
#include <stdio.h>
int main() {
    int a = 5, b = 10;
    printf("Before swap: a=%d, b=%d\n", a, b);

    a = a ^ b;
    b = a ^ b;
    a = a ^ b;

    printf("After swap: a=%d, b=%d\n", a, b);
    return 0;
}
```
47) Implement a program to check if a number is even or odd using the modulus operator.
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
48) Write a C program that uses the bitwise operators to check if a given positive integer is divisible by both 6 and 9.
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);

    // Divisible by both 6 and 9 → divisible by LCM(6,9)=18
    if ((n % 18) == 0)
        printf("Divisible by both 6 and 9\n");
    else
        printf("Not divisible by both 6 and 9\n");

    return 0;
}
```
49) Develop a program to find the maximum of three numbers using the conditional operator.
```
#include <stdio.h>
int main() {
    int a, b, c, max;
    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    max = (a > b) ? ( (a > c) ? a : c ) : ( (b > c) ? b : c );
    printf("Maximum = %d\n", max);
    return 0;
}
```
50) Implement a program that checks if a number is less than 50 without using the less than operator.
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter number: ");
    scanf("%d", &n);

    if (!(n >= 50))
        printf("Number is less than 50\n");
    else
        printf("Number is not less than 50\n");

    return 0;
}
```
51) What would be the value of `a`?

a)  
```
int a = 10/45*23%45/(45%4*21);

Answer: a = 0
```
b)

```
float a = 10 + 45.0 * 23 - 45 + (4 * 21.0);

Final: 1000 + 84 = 1084

 Answer: a = 1084.0
```
52) Check if the given number is a palindrome in binary using bitwise operators
```
#include <stdio.h>
int isBinaryPalindrome(unsigned int n) {
    unsigned int rev = 0, temp = n;
    while (temp) {
        rev = (rev << 1) | (temp & 1);
        temp >>= 1;
    }
    return n == rev;
}
int main() {
    int n;
    scanf("%d", &n);
    if (isBinaryPalindrome(n))
        printf("Palindrome in binary\n");
    else
        printf("Not palindrome in binary\n");
    return 0;
}
```
53) Rotate bits of a number to the left by d positions
```
#include <stdio.h>
#define INT_BITS 32

unsigned int rotateLeft(unsigned int n, unsigned int d) {
    return (n << d) | (n >> (INT_BITS - d));
}

int main() {
    unsigned int n, d;
    scanf("%u %u", &n, &d);
    printf("Result = %u\n", rotateLeft(n, d));
    return 0;
}
```
54) Reverse bits of a number
```
#include <stdio.h>
unsigned int reverseBits(unsigned int n) {
    unsigned int rev = 0;
    for (int i = 0; i < 32; i++) {
        rev <<= 1;
        rev |= (n & 1);
        n >>= 1;
    }
    return rev;
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("Reversed = %u\n", reverseBits(n));
    return 0;
}
```
55) Check if a number has alternate bits set
```
#include <stdio.h>
int hasAlternateBits(unsigned int n) {
    unsigned int x = n ^ (n >> 1);
    return (x & (x + 1)) == 0;
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    if (hasAlternateBits(n))
        printf("Yes, alternate bits set\n");
    else
        printf("No\n");
    return 0;
}
```
56) Count bits needed to convert A → B
```
#include <stdio.h>
int countBits(int a, int b) {
    int x = a ^ b, count = 0;
    while (x) {
        x &= (x - 1);
        count++;
    }
    return count;
}
int main() {
    int a, b;
    scanf("%d %d", &a, &b);
    printf("Bits needed = %d\n", countBits(a, b));
    return 0;
}
```
57) Check if a number is power of 4
```
#include <stdio.h>
int isPowerOf4(unsigned int n) {
    return (n > 0) && !(n & (n - 1)) && (n & 0x55555555);
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    if (isPowerOf4(n)) printf("Power of 4\n");
    else printf("Not power of 4\n");
    return 0;
}
```
58) Swap adjacent bits
```
#include <stdio.h>
unsigned int swapAdjacentBits(unsigned int n) {
    return ((n & 0xAAAAAAAA) >> 1) | ((n & 0x55555555) << 1);
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("After swap = %u\n", swapAdjacentBits(n));
    return 0;
}
```
59) Check if number is perfect square using bitwise operators
(Bitwise trick: A perfect square has odd count of factors. But simplest safe way is check sqrt)

```
#include <stdio.h>
#include <math.h>
int isPerfectSquare(int n) {
    int r = (int)sqrt(n);
    return r * r == n;
}
int main() {
    int n;
    scanf("%d", &n);
    if (isPerfectSquare(n)) printf("Perfect Square\n");
    else printf("Not Perfect Square\n");
    return 0;
}
```
60) Swap first and last bits of a number
```
#include <stdio.h>
unsigned int swapFirstLast(unsigned int n, int bits) {
    unsigned int first = (n >> (bits - 1)) & 1;
    unsigned int last = n & 1;
    if (first != last) {
        n ^= (1 << (bits - 1));
        n ^= 1;
    }
    return n;
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("After swap = %u\n", swapFirstLast(n, 32));
    return 0;
}
```
61) Count bits to be flipped to convert A → B
```
#include <stdio.h>
int countFlips(int a, int b) {
    int x = a ^ b, count = 0;
    while (x) {
        x &= (x - 1);
        count++;
    }
    return count;
}
int main() {
    int a, b;
    scanf("%d %d", &a, &b);
    printf("Flips needed = %d\n", countFlips(a, b));
    return 0;
}
```
62) Check if number is power of 8
```
#include <stdio.h>
int isPowerOf8(unsigned int n) {
    return (n > 0) && !(n & (n - 1)) && (n % 8 == 0);
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    if (isPowerOf8(n)) printf("Power of 8\n");
    else printf("Not power of 8\n");
    return 0;
}
```
63) Set all bits at odd positions
```
#include <stdio.h>
unsigned int setOddBits(unsigned int n) {
    return n | 0xAAAAAAAA;
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("After setting odd bits = %u\n", setOddBits(n));
    return 0;
}
```
64) Count set bits in sum of two numbers
```
#include <stdio.h>
int countSetBits(int n) {
    int count = 0;
    while (n) {
        n &= (n - 1);
        count++;
    }
    return count;
}
int main() {
    int a, b, sum;
    scanf("%d %d", &a, &b);
    sum = a + b;
    printf("Set bits in sum = %d\n", countSetBits(sum));
    return 0;
}
```
65) Check if number is power of 16
```
#include <stdio.h>
int isPowerOf16(unsigned int n) {
    return (n > 0) && !(n & (n - 1)) && (n & 0x11111111);
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    if (isPowerOf16(n)) printf("Power of 16\n");
    else printf("Not power of 16\n");
    return 0;
}
```
66) Swap bits at even and odd positions
```
#include <stdio.h>
unsigned int swapEvenOdd(unsigned int n) {
    return ((n & 0xAAAAAAAA) >> 1) | ((n & 0x55555555) << 1);
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("After swap = %u\n", swapEvenOdd(n));
    return 0;
}
```
67) Toggle bits at odd positions
```
#include <stdio.h>
unsigned int toggleOddBits(unsigned int n) {
    return n ^ 0xAAAAAAAA;
}
int main() {
    unsigned int n;
    scanf("%u", &n);
    printf("After toggle = %u\n", toggleOddBits(n));
    return 0;
}
```
