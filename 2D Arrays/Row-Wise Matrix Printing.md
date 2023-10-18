# Row-Wise Matrix Printing - Editorial

## Problem Analysis:
This problem is straightforward. You're given a matrix of 'N' rows and 'M' columns, and your task is to print the elements of this matrix row by row. This exercise is perfect for beginners to practice matrix traversal and command-line output.

## Prerequisites:
- Understanding of 2D arrays (matrices)
- Basic loop constructs

## Problem Statement:
You are tasked with printing each row of a given 'N' x 'M' matrix. The problem is simple and direct, focusing on matrix traversal without any need for data manipulation.

## Constraints:
- 1 <= N <= 100
- 1 <= M <= 100
- 1 <= mat[i][j] <= 10000

These constraints indicate that the task will not involve large data sets or require optimization. Instead, it focuses on the fundamentals of matrix traversal and output.

## Solution Approach:
The solution involves basic steps:
1. Iterating through each row of the matrix.
2. Within each row, iterating through each column.
3. Printing the current element.
4. Moving to the next line after processing each row.

## Pseudo Code:

<pre><code>
read N, M
initialize a 2D array 'matrix' of dimensions N x M

// Reading the matrix
for i = 0 to N-1 do
    for j = 0 to M-1 do
        read matrix[i][j]
    end for
end for

// Printing the matrix row by row
for i = 0 to N-1 do
    for j = 0 to M-1 do
        print matrix[i][j], without newline
        if j < M-1 then
            print " ", without newline // Print a space between elements of the same row
        end if
    end for
    print newline // Move to the next row after printing all columns of the current row
end for
</code></pre>

## Time Complexity:
O(N*M), where you must visit each element once. The number of elements is the product of the number of rows 'N' and the number of columns 'M'.

## Space Complexity:
O(N*M), for storing the matrix. No additional significant space is used.

## Sample Code in Java:

```java
import java.util.Scanner;

public class RowWiseMatrixPrinting {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int M = scanner.nextInt();
        int[][] matrix = new int[N][M];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        // Printing the matrix row by row
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                System.out.print(matrix[i][j]);
                if (j < M - 1) {
                    System.out.print(" "); // Print a space between elements of the same row
                }
            }
            System.out.println(); // Move to the next row
        }

        scanner.close();
    }
}
