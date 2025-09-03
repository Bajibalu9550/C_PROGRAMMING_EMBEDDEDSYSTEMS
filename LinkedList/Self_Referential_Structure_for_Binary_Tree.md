# C Program: Self-Referential Structure for a Binary Tree Node

```c
#include <stdio.h>
#include <stdlib.h>

struct TreeNode {
    int data;
    struct TreeNode *left;
    struct TreeNode *right;
};

int main() {
   
    struct TreeNode *root = (struct TreeNode *)malloc(sizeof(struct TreeNode));
    if (root == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    root->data = 10;
    root->left = NULL;
    root->right = NULL;

    printf("Root node data: %d\n", root->data);

    free(root);
    return 0;
}
