  #include <stdio.h>

int main() {
    int m, n, k;
    
    
    printf("Enter rows and columns for first matrix (m n): ");
    scanf("%d %d", &m, &n);
    
    printf("Enter columns for second matrix (k): ");
    scanf("%d", &k);
    
    int matrix1[m][n], matrix2[n][k], result[m][k];
    
    
    printf("Enter elements of first matrix (%d x %d):\n", m, n);
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < n; j++) {
            printf("Element [%d][%d]: ", i+1, j+1);
            scanf("%d", &matrix1[i][j]);
        }
    }
    
    
    printf("Enter elements of second matrix (%d x %d):\n", n, k);
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < k; j++) {
            printf("Element [%d][%d]: ", i+1, j+1);
            scanf("%d", &matrix2[i][j]);
        }
    }
    
    
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < k; j++) {
            result[i][j] = 0;  // مقداردهی اولیه
            for (int x = 0; x < n; x++) {
                result[i][j] += matrix1[i][x] * matrix2[x][j];
            }
        }
    }
    
    
    printf("Resultant matrix (%d x %d):\n", m, k);
    for (int i = 0; i < m; i++) {
        for (int j = 0; j < k; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}
