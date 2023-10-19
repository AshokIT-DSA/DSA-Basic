### **Matrix Row and Column Sums - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Loops, Matrix Manipulation, Basic Arithmetic

### Problem Statement:
This problem requires participants to develop a program that processes a matrix 'A' of size 'N x M'. The primary objective is to calculate the sum of elements for each row and each column, compiling these sums into a single array. The first 'N' elements of this array should be the sums of the rows, followed by 'M' elements that are the sums of the columns.

### Detailed Explanation:

1. **Understanding the Task:**
   The challenge lies in correctly iterating over the matrix and performing the summations without mixing row sums with column sums. A clear understanding of how matrix indexing works is essential to achieving this.

2. **Solution Approach:**
   We initialize an array 'sums' of size 'N + M' to store the results. We then iterate through matrix 'A', calculating the sum of elements for each row and storing them in the first 'N' positions of 'sums'. Subsequently, we proceed to calculate the sum of elements for each column, placing these in the next 'M' positions of 'sums'.

3. **Problem Constraints:**
   - The matrix dimensions 'N' and 'M' satisfy 1 <= N, M <= 1000.
   - Each matrix element 'A[i][j]' is an integer such that 1 <= A[i][j] <= 1000.
   
   These constraints ensure we avoid issues with excessively large inputs or overflows. They also imply the need for efficient iteration, as the matrix size can be substantial.

## Pseudo Code:

<pre><code>
read N, M
initialize matrix 'A' of dimensions N x M
initialize array 'sums' of size N + M

// Summing each row's elements
for i = 0 to N-1 do:
    rowSum = 0
    for j = 0 to M-1 do:
        rowSum += A[i][j]
    end for
    sums[i] = rowSum
end for

// Summing each column's elements
for j = 0 to M-1 do:
    colSum = 0
    for i = 0 to N-1 do:
        colSum += A[i][j]
    end for
    sums[N + j] = colSum
end for

print sums
</code></pre>

### Time Complexity:
O(N * M) because the solution involves nested loops that iterate through each element of the matrix once, both for row sums and column sums. This linear traversal ensures efficiency and compliance with the size constraints.

### Space Complexity:
O(N + M) due to the 'sums' array. We are storing 'N' row sums and 'M' column sums, with no additional significant space usage. The space taken by the matrix is not considered in the calculation.

## Sample Code (Java):

```java
import java.util.Scanner;

public class MatrixRowColumnSum {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int M = scanner.nextInt();
        int[][] A = new int[N][M];
        int[] sums = new int[N + M];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                A[i][j] = scanner.nextInt();
            }
        }

        // Calculating row sums
        for (int i = 0; i < N; i++) {
            int rowSum = 0;
            for (int j = 0; j < M; j++) {
                rowSum += A[i][j];
            }
            sums[i] = rowSum;
        }

        // Calculating column sums
        for (int j = 0; j < M; j++) {
            int colSum = 0;
            for (int i = 0; i < N; i++) {
                colSum += A[i][j];
            }
            sums[N + j] = colSum;
        }

        // Output the sums
        for (int sum : sums) {
            System.out.print(sum + " ");
        }
    }
}
