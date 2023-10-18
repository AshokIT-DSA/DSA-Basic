### **Matrix Addition - Editorial**

## Difficulty: Easy

## Prerequisites: Two-dimensional Arrays, Looping constructs, Basic Input/Output, Matrix Operations

### Problem Statement:
Participants are tasked with adding two matrices, 'A' and 'B,' provided they are of the same dimensions. The resulting matrix will contain elements that are the sum of the corresponding elements from 'A' and 'B.'

### Detailed Explanation:

1. **Understanding the Task:**
   The problem is a fundamental one involving matrix operations. It requires the participant to understand how to traverse a two-dimensional array and perform addition operations on the elements.

2. **Solution Approach:**
   The solution involves reading the matrices' dimensions and their elements. A result matrix is initialized with the same dimensions. The program then iterates through each element in the matrices, adds the corresponding elements, and stores the sum in the new matrix.

3. **Problem Constraints:**
   - The dimensions 'N' and 'M' are such that 1 <= N, M <= 1000.
   - Elements of the matrices, A[i][j] and B[i][j], are such that 1 <= A[i][j], B[i][j] <= 10000.

## Pseudo Code:

<pre><code>
read N, M
initialize matrixA, matrixB, and resultMatrix of dimensions N x M

// Reading matrix A and B
for i = 0 to N-1 do
    for j = 0 to M-1 do
        read matrixA[i][j]
        read matrixB[i][j]
    end for
end for

// Calculating and forming the resultMatrix
for i = 0 to N-1 do
    for j = 0 to M-1 do
        resultMatrix[i][j] = matrixA[i][j] + matrixB[i][j]
    end for
end for

// Output resultMatrix (implementation-dependent)
</code></pre>

### Time Complexity:
O(N*M), due to the nested iteration through each element in the 'N x M' matrices to perform the addition.

### Space Complexity:
O(N*M), necessary for the storage of 'N x M' matrices and the additional space for the resultMatrix.

## Sample Code (Java):

```java
import java.util.Scanner;

public class MatrixAddition {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int M = scanner.nextInt();
        int[][] matrixA = new int[N][M];
        int[][] matrixB = new int[N][M];
        int[][] resultMatrix = new int[N][M];

        // Reading the matrices
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                matrixA[i][j] = scanner.nextInt();
                matrixB[i][j] = scanner.nextInt();
            }
        }

        // Calculating the resultMatrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                resultMatrix[i][j] = matrixA[i][j] + matrixB[i][j];
            }
        }

        // (Optional) Printing the resultMatrix
        // Implementation of this part can vary depending on the specific requirements of the problem (like format of output).
    }
}
