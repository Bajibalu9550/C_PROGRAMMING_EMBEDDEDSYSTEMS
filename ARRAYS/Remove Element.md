#  Remove Element

This C program removes all occurrences of a specific value from an array **in-place**  
and returns the new length of the modified array.

##  Full Code

```c
#include <stdio.h>

int removeElement(int* nums, int size, int val) {
    int k = 0;
    for (int i = 0; i < size; i++) {
        if (nums[i] != val) {
            nums[k] = nums[i];
            k++;
        }
    }
    return k;
}

int main() {
    int nums[] = {3, 2, 2, 3};
    int size = sizeof(nums) / sizeof(nums[0]);
    int val = 3;

    int k = removeElement(nums, size, val);

    printf("New length: %d\n", k);
    printf("Modified array: ");
    for (int i = 0; i < k; i++) {
        printf("%d ", nums[i]);
    }
    printf("\n");

    return 0;
}

 Examples

 Example 1

**Input:**  
`nums = [3, 2, 2, 3]`, `val = 3`

**Output:**  
`2, nums = [2, 2, _, _]`

**Explanation:**  
Your function should return `k = 2`, with the first two elements of `nums` being `2`.  
It does not matter what you leave beyond the returned `k` (hence they are underscores).

---

 Example 2

**Input:**  
`nums = [0, 1, 2, 2, 3, 0, 4, 2]`, `val = 2`

**Output:**  
`5, nums = [0, 1, 4, 0, 3, _, _, _]`

**Explanation:**  
Your function should return `k = 5`, with the first five elements of `nums` containing `0`, `1`, `4`, `0`, and `3`.  
Note that the five elements can be returned in **any order**.  
It does not matter what you leave beyond the returned `k` (hence they are underscores).
