# C Program to Generate and Print an n x n Spiral Matrix

```c
#include<stdio.h>

int main(){
    int n;
    printf("Enter Number: ");
    scanf("%d",&n);

    int m[n][n];
    int num = 1;
    int top = 0, bottom = n - 1;
    int left = 0, right = n - 1;

    while(top <= bottom && left <= right){
       
        for(int i = left; i <= right; i++)
            m[top][i] = num++;
        top++;

        
        for(int i = top; i <= bottom; i++)
            m[i][right] = num++;
        right--;

       
        if(top <= bottom){
            for(int i = right; i >= left; i--)
                m[bottom][i] = num++;
            bottom--;
        }

        
        if(left <= right){
            for(int i = bottom; i >= top; i--)
                m[i][left] = num++;
            left++;
        }
    }

    
    printf("Spiral Matrix : \n");
    for(int i = 0; i < n; i++){
        for(int j = 0; j < n; j++){
            printf("%d ", m[i][j]);
        }
        printf("\n");
    }
}
```
