#  Longest Substring without Repeating Characters

This C program finds the length of the **longest substring** without repeating characters using a sliding window approach.

##  Full Code

```c
#include <stdio.h>
#include <string.h>

int lengthOfLongestSubstring(char* s) {
    int n = strlen(s);
    int max = 0, start = 0;
    int chara[128];
    for (int i = 0; i < 128; i++) {
        chara[i] = -1;
    }
    for (int i = 0; i < n; i++) {
        if (chara[s[i]] != -1 && chara[s[i]] >= start) {
            start = chara[s[i]] + 1;
        }
        chara[s[i]] = i;
        max = (i - start + 1 > max) ? i - start + 1 : max;
    }
    return max;
}

int main() {
    char s[] = "abcabcbb";
    int length = lengthOfLongestSubstring(s);
    printf("Length of longest substring without repeating characters: %d\n", length);
    return 0;
}


Example
Input:
s = "abcabcbb"
Output:
Length of longest substring without repeating characters: 3
