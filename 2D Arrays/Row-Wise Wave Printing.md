# Row-Wise Wave Printing - Editorial

## Problem Analysis:
This problem requires participants to understand how to manipulate the traversal of a two-dimensional array, creating a wave-like pattern row-wise. The challenge lies in alternating the printing direction between rows, which differs from standard row-wise traversal.

## Prerequisites:
- Understanding of loops (for, while)
- Familiarity with arrays, particularly two-dimensional arrays
- Basic control flow (if-else conditions)

## Problem Statement:
Given an 'N*N' matrix, the task is to print the elements in a wave-like pattern starting from the first row. When you reach the end of a row, move down to the next row, but this time, traverse backwards. Continue this alternate traversal for every row.

## Constraints:
- 1 <= N <= 1000
- 0 <= Mat[i][j] <= 1000

These constraints indicate that the input size wouldn’t be too large, making it less likely for the program to hit memory limits or experience high execution times.

## Solution Approach:
The approach is to traverse the matrix in a row-wise manner but print the elements in a zigzag way:
1. If the current row number is odd, we print the elements from left to right.
2. If the current row number is even, we print the elements from right to left.

This way, we achieve the wave-like pattern across the rows.

## Pseudo Code:

<pre><code>
read N
initialize a 2D array 'matrix' of dimensions N x N

// Reading the matrix
for i = 0 to N-1 do
    for j = 0 to N-1 do
        read matrix[i][j]
    end for
end for

// Printing the matrix in a wave pattern
for i = 0 to N-1 do
    if i is even then
        for j = 0 to N-1 do
            print matrix[i][j]
        end for
    else
        for j = N-1 to 0 do
            print matrix[i][j]
        end for
    end if
end for
</code></pre>

## Time Complexity:
O(N^2), because each element of the matrix is visited exactly once, regardless of the printing direction.

## Space Complexity:
O(N^2), as we're storing the entire matrix. There are no additional data structures consuming significant memory.

## Sample Code in Java:

```java
import java.util.Scanner;

public class RowWiseWavePrinting {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[][] matrix = new int[N][N];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        // Printing the matrix in a wave pattern
        for (int i = 0; i < N; i++) {
            if (i % 2 == 0) {
                for (int j = 0; j < N; j++) {
                    System.out.print(matrix[i][j] + " ");
                }
            } else {
                for (int j = N - 1; j >= 0; j--) {
                    System.out.print(matrix[i][j] + " ");
                }
            }
        }
        scanner.close();
    }
}
