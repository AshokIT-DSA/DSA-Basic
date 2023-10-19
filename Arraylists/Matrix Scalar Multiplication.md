# Matrix Scalar Multiplication - Editorial

## Difficulty: Easy

## Prerequisites: Matrices, Loops

### Problem Statement:
This task requires participants to implement a program that performs a matrix scalar multiplication. The program will receive a square matrix 'A' of dimensions 'N x N' and an integer 'B'. The objective is to multiply every element inside matrix 'A' by the scalar value 'B'.

### Constraints:
- 1 <= N, B <= 1000
- 0 <= Mat[i][j] <= 1000

### Detailed Explanation:

1. **Understanding the Task:**
   Scalar multiplication of a matrix is a basic operation where every element of the matrix is multiplied by a given scalar. This problem requires a fundamental understanding of matrix operations and how to iterate through a matrix.

2. **Solution Approach:**
   The solution begins by reading the dimensions 'N' and the scalar 'B', followed by the elements of matrix 'A'. We then use nested loops to iterate through the matrix, performing the multiplication. It's important to maintain the structure of the matrix, meaning that the scalar multiplication doesn't change the dimensions of 'N x N' but alters each element's value.

3. **Algorithm Steps:**
   - Read the input values.
   - Initialize the matrix 'A' with the given input.
   - Traverse each element in 'A' using nested loops.
   - For each element, perform the scalar multiplication.
   - Store the result in a new matrix or update the existing matrix (based on requirements/preferences).
   - Output/return the resultant matrix.

4. **Problem Constraints:**
   The constraints ensure that the problem remains within a manageable computational complexity. It implies that even with the maximum values, the program should execute efficiently without excessive memory usage.

## Pseudo Code:

<pre><code>
read N, B
initialize matrix 'A' of dimensions N x N

for i = 0 to N-1 do:
    for j = 0 to N-1 do:
        A[i][j] = A[i][j] * B  // Scalar multiplication for each element.
    end for
end for

print/output matrix 'A'
</code></pre>

### Time Complexity

O(N^2), due to the nested loops that iterate through each element of the matrix to perform the multiplication.

### Space Complexity

O(1), if we're updating the matrix in place, excluding the input space. If a new matrix is used to store the results, the space complexity would be O(N^2).

## Java Implementation

```java
import java.util.Scanner;

public class MatrixScalarMultiplication {
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Reading the dimensions of the matrix and the scalar
        int N = scanner.nextInt(); // The dimension of the matrix
        int B = scanner.nextInt(); // The scalar value

        // Initializing the matrix
        int[][] matrix = new int[N][N];

        // Reading the matrix data
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        // Perform the scalar multiplication
        scalarMultiplyMatrix(N, B, matrix);

        // Printing the result
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
    
    // Method to perform scalar multiplication on a matrix
    public static void scalarMultiplyMatrix(int N, int B, int[][] matrix) {
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                matrix[i][j] *= B; // Multiply each element by the scalar B
            }
        }
    }
}