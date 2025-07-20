# TRANSPOSE-AND-ROW-WISE-REVERSE-IN-C-
Transpose + Row-wise Reverse is a process where the matrix is first transposed (rows become columns), and then each resulting row is reversed individually. This operation is commonly used in graphics, image rotations, and matrix manipulations.
```
#include <stdio.h>

int main() {
    int rows, cols;
    printf("Enter number of rows and columns: ");
    scanf("%d %d", &rows, &cols);

    int matrix[100][100], transposed[100][100];

    // Input the matrix
    printf("Enter elements of the matrix:\n");
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    // Transpose the matrix
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            transposed[j][i] = matrix[i][j];
        }
    }

    // Reverse the rows of the transposed matrix
    for(int i = 0; i < cols / 2; i++) {
        for(int j = 0; j < rows; j++) {
            int temp = transposed[i][j];
            transposed[i][j] = transposed[cols - 1 - i][j];
            transposed[cols - 1 - i][j] = temp;
        }
    }

    // Print the final result
    printf("Output matrix is:\n");
    for(int i = 0; i < cols; i++) {
        for(int j = 0; j < rows; j++) {
            printf("%d\t", transposed[i][j]);
        }
        printf("\n");
    }

    return 0;
}
