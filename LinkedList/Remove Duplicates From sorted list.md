# Remove Duplicates from Sorted Linked List

This program removes duplicates from a *sorted singly linked list* in C.

###  C Code

```c
#include <stdlib.h>

struct ListNode {
    int val;
    struct ListNode* next;
};

struct ListNode* deleteDuplicates(struct ListNode* head) {
    struct ListNode* curr = head;
    while (curr && curr->next) {
        if (curr->val == curr->next->val) {
            struct ListNode* dup = curr->next;
            curr->next = dup->next;
            free(dup);
        } else {
            curr = curr->next;
        }
    }
    return head;
}



Linked List Example 1:
The input linked list:

1 → 1 → 1
After removing duplicates:
1

Example 2:

**Before:**

1 → 2 → 2 → 3 → 3 → 3 → 4

**After:**

1 → 2 → 3 → 4

