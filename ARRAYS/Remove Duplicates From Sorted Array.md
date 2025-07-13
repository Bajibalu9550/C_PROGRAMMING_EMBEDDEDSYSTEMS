#  Remove Duplicates From Sorted Array

This C program removes duplicates from a **sorted array** in-place and returns the length of the updated array with only unique elements.

##  Full Code

```c
#include <stdio.h>

int removeDuplicates(int* nums, int size) {
    if (size == 0) {
        return 0;
    }
    int i = 0;
    for (int j = 1; j < size; j++) {
        if (nums[j] != nums[i]) {
            ++i;
            nums[i] = nums[j];
        }
    }
    return i + 1;
}

int main() {
    int nums[] = {1, 1, 2, 2, 3, 3, 4};
    int size = sizeof(nums) / sizeof(nums[0]);

    int newLength = removeDuplicates(nums, size);

    printf("New length: %d\n", newLength);
    printf("Modified array: ");
    for (int i = 0; i < newLength; i++) {
        printf("%d ", nums[i]);
    }
    printf("\n");

    return 0;
}


Example
Input:
nums = [1, 1, 2, 2, 3, 3, 4]
Output:
New length: 4
Modified array: 1 2 3 4
