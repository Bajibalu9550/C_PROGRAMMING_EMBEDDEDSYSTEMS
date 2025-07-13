#  Search in Rotated Sorted Array (Linear Search Approach)

This program performs a **linear search** in a rotated sorted array.  
Although binary search is typically preferred for such problems (for O(log n) complexity), this version uses a simple linear search for clarity and ease of implementation.

##  Code

```c
#include <stdio.h>
#include <stdbool.h>

bool search(int* nums, int numsSize, int target) {
    for (int i = 0; i < numsSize; i++) {
        if (nums[i] == target) {
            return true;
        }
    }
    return false;
}

int main() {
    int nums[] = {4, 5, 6, 7, 0, 1, 2}; 
    int numsSize = sizeof(nums) / sizeof(nums[0]);
    int target = 0;

    if (search(nums, numsSize, target)) {
        printf("True");
    } else {
        printf("False");
    }

    return 0;
}



  Examples

 Example 1:
**Input:**  
`nums = [2, 5, 6, 0, 0, 1, 2]`, `target = 0`  
**Output:**  
`true`

---

 Example 2:
**Input:**  
`nums = [2, 5, 6, 0, 0, 1, 2]`, `target = 3`  
**Output:**  
`false`

