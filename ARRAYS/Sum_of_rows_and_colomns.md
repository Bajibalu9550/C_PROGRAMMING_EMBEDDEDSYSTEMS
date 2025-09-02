# C Program to Find the Sum of Rows and Columns of a 2-D Array

```c
#include<stdio.h>

int main(){
    int m, n;
    printf("Enter Number of rows and colomns: ");
    scanf("%d%d", &m, &n);

    int a[m+1][n+1]; 

    
    for(int i = 0; i < m; i++){
        for(int j = 0; j < n; j++){
            scanf("%d", &a[i][j]);
        }
    }

    
    for(int i = 0; i <= m; i++)
        a[i][n] = 0;
    for(int j = 0; j <= n; j++)
        a[m][j] = 0;

    
    for(int i = 0; i < m; i++){
        for(int j = 0; j < n; j++){
            a[i][n] += a[i][j];  
            a[m][j] += a[i][j];  
            a[m][n] += a[i][j];   
        }
    }

   
    printf("Array Elements: \n");
    for(int i = 0; i <= m; i++){
        for(int j = 0; j <= n; j++){
            printf("%d ", a[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
