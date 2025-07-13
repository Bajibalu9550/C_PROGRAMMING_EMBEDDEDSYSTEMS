#  Find First and Last Positions of Element

This C program finds the **first** and **last** positions of a given target element in an array.  
It returns `[-1, -1]` if the target is not found.

##  Code

```c
#include <stdio.h>
#include <stdlib.h>

int* searchRange(int* nums, int numsSize, int target, int* returnSize) {
    int *result = (int *)malloc(2 * sizeof(int));
    int f = -1, l = -1;
    *returnSize = 2;

    for (int i = 0; i < numsSize; i++) {
        if (nums[i] == target) {
            f = i;
            break;
        }
    }

    for (int i = numsSize - 1; i >= 0; i--) {
        if (nums[i] == target) {
            l = i;
            break;
        }
    }

    result[0] = f;
    result[1] = l;
    return result;
}

int main() {
    int nums[] = {5, 7, 7, 8, 8, 10};
    int target = 8;
    int returnSize;
    
    int* positions = searchRange(nums, sizeof(nums)/sizeof(nums[0]), target, &returnSize);
    
    printf("First and last positions of %d: [%d, %d]\n", target, positions[0], positions[1]);

    free(positions);
    return 0;
}


Example 1
Input:
nums = [5, 7, 7, 8, 8, 10], target = 8

Output:
[3, 4]

Example 2
Input:
nums = [5, 7, 7, 8, 8, 10], target = 6

Output:
[-1, -1]
