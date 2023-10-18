# Column-Wise Wave Printing - Editorial

## Problem Analysis:
This problem requires participants to manipulate a two-dimensional array (matrix) and understand the logic behind traversing it in a specific, non-traditional manner. The task is to print the matrix in a wave-like form but column-wise, which introduces an element of pattern recognition and control flow manipulation within the context of matrix traversal.

## Prerequisites:
- Basic understanding of loops and conditionals
- Knowledge of 2D arrays (matrices) and how to traverse them
- Pattern recognition

## Problem Statement:
You will print a given 'N*N' matrix in a column-wise wave pattern. This requirement means you won't print in the traditional horizontal or vertical sequence but will follow a 'zigzag' pattern within the columns, alternating between moving downwards and upwards from one column to the next.

## Constraints:
- 1 <= N <= 100
- 0 <= Mat[i][j] <= 10^8

Given these constraints, the problem will not require optimizing for very large inputs. The main challenge is figuring out the correct sequence to print the elements based on the described pattern.

## Solution Approach:
To solve this problem, a nested loop approach will be used with conditional direction switching:

1. Traverse each column, starting from the first.
2. For the current column, if it's an odd-numbered column (1-indexed), print from the top to bottom. If it's even-numbered, print from bottom to top.
3. Continue this pattern for all columns until the entire matrix is printed.

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
for j = 0 to N-1 do
    if j is even then
        // Top to bottom
        for i = 0 to N-1 do
            print matrix[i][j]
        end for
    else
        // Bottom to top
        for i = N-1 to 0 do
            print matrix[i][j]
        end for
    end if
end for
</code></pre>

## Time Complexity:
O(N^2), where 'N' is the number of rows/columns in the matrix. This is because every element is visited exactly once during the printing process.

## Space Complexity:
O(N^2) for storing the matrix. No additional significant space is used.

## Sample Code in Java:

```java
import java.util.Scanner;

public class ColumnWiseWavePrinting {

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
        for (int j = 0; j < N; j++) {
            if (j % 2 == 0) {
                // Top to bottom
                for (int i = 0; i < N; i++) {
                    System.out.print(matrix[i][j] + " ");
                }
            } else {
                // Bottom to top
                for (int i = N - 1; i >= 0; i--) {
                    System.out.print(matrix[i][j] + " ");
                }
            }
        }
        scanner.close();
    }
}
