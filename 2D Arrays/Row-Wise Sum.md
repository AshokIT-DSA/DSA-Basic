### **Row-Wise Sum - Editorial**

## Difficulty: Easy

## Prerequisites: Two-dimensional Arrays, Looping constructs, Basic Input/Output

### Problem Statement:
Participants are provided with an integer 'N' representing the dimensions of a square matrix, and the 'N*N' matrix itself. The primary task is to compute and print the sum of elements for each row of the matrix. Each sum corresponds to a single row, and the sequence of printing should align with the row orders in the matrix.

### Detailed Explanation:

1. **Understanding the Task:**
   The problem requires fundamental interaction with a two-dimensional array or matrix. Participants must traverse the matrix, compute the sum of elements row-wise, and print the results. Understanding how to navigate through a 2D array and perform arithmetic operations is essential.

2. **Solution Approach:**
   We initiate by reading the matrix dimensions and the matrix itself. Subsequently, using nested loops, we iterate across each row and, within that, across each column. While traversing columns, we accumulate the sum of elements present in the current row. After completing each row, we print the sum, reset the accumulator, and proceed with the next row.

3. **Problem Constraints:**
   - 'N' is an integer such that 1 <= N <= 1000.
   - Matrix elements (Mat[i][j]) are integers such that 0 <= Mat[i][j] <= 1000.

   These constraints ensure participants deal with medium-sized input without the complexity of large numbers or high-performance requirements.

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

// Calculating and printing row-wise sum
for i = 0 to N-1 do
    initialize 'sum' to 0
    for j = 0 to N-1 do
        sum = sum + matrix[i][j]
    end for
    print sum
end for
</code></pre>

### Time Complexity:
O(N^2), due to the nested iteration over the 'N*N' matrix, ensuring each element is accessed and processed for the row sum calculation.

### Space Complexity:
O(N^2), needed for the storage of the 'N*N' matrix. No additional space complexity as the sum accumulator uses constant space, resetting after each row computation.

## Sample Code (Java):

```java
import java.util.Scanner;

public class RowWiseSum {
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

        // Calculating and printing row-wise sum
        for (int i = 0; i < N; i++) {
            int sum = 0;
            for (int j = 0; j < N; j++) {
                sum += matrix[i][j];
            }
            System.out.println(sum);
        }
    }
}
