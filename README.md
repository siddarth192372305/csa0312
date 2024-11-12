#include <stdio.h>

#define ROW1 3
#define COL1 2
#define ROW2 COL1
#define COL2 4

void multiplyMatrices(int mat1[][COL1], int mat2[][COL2], int res[][COL2]) {
    int i, j, k;

    for (i = 0; i < ROW1; i++) {
        for (j = 0; j < COL2; j++) {
            res[i][j] = 0;
            for (k = 0; k < ROW2; k++) {
                res[i][j] += mat1[i][k] * mat2[k][j];
            }
        }
    }
}

int main() {
    int mat1[ROW1][COL1] = {{1, 2}, {3, 4}, {5, 6}};
    int mat2[ROW2][COL2] = {{7, 8, 9, 10}, {11, 12, 13, 14}};
    int res[ROW1][COL2];

    multiplyMatrices(mat1, mat2, res);

    printf("Resultant matrix:\n");
    for (int i = 0; i < ROW1; i++) {
        for (int j = 0; j < COL2; j++) {
            printf("%d ", res[i][j]);
        }
        printf("\n");
    }

    return 0;
}
