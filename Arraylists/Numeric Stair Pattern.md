# Numeric Stair Pattern

## Difficulty: 
Easy

## Problem Statement:
Given an integer `N`, your task is to generate a pattern in a 2D array with `N` rows, where each row `i` contains numbers from 1 to `i`. The pattern should resemble a staircase structure when printed, incrementing each row by one number from the previous row.

### Constraints:
- 1 <= `N` <= 1000

### Detailed Explanation:

Your approach to solving this problem should involve the following steps:

1. **Understanding the Pattern**:
   The pattern requires that for each row `i` (1-indexed), you print integers from 1 up to `i`. This forms a staircase pattern where each step increases by one number.

2. **Solution Approach**:
   Initialize an empty 2D array or list of lists. You will then need two nested loops. The outer loop will iterate from 1 to `N`, representing each row. The inner loop will iterate from 1 to `i`, filling each row with the numbers in the current range.

3. **Generating the Pattern**:
   - In each iteration of the outer loop, initialize an empty row.
   - In the inner loop, append the numbers from 1 to `i` to the current row.
   - After the inner loop, append the current row to the 2D array or list of lists.

4. **Output**:
   - Print or return the 2D array, depending on requirements. If printed directly, it should display the staircase pattern of numbers.

### Pseudo Code:

<pre><code>
read N
initialize stairs as empty list of lists

for i = 1 to N do:
    initialize currentRow as empty list
    for j = 1 to i do:
        add j to currentRow
    end for
    add currentRow to stairs
end for

return or print stairs
</code></pre>

## Complexity Analysis:
- **Time Complexity**: O(N^2) 
    - The nested loops cause the operations to grow quadratically with the input size `N`, leading to a time complexity of O(N^2).

- **Space Complexity**: O(1)
    - The space complexity is O(1) because there is no additional data structure used that grows with the input size. Although the problem description mentions a 2D array, the solution itself does not store any such structure; it directly prints the output.

## Java Solution:

```java
import java.util.Scanner;

public class NumericStairPattern {

    public static void main(String[] args) {
        // Scanner object for input
        Scanner scanner = new Scanner(System.in);

        // Read N
        int N = scanner.nextInt();

        // Close the scanner as we no longer need it
        scanner.close();

        // Generate and print the numeric stair pattern
        generateAndPrintStairs(N);
    }

    public static void generateAndPrintStairs(int N) {
        // Iterating through each level of the stair
        for (int i = 1; i <= N; i++) {
            // Iterating through each number in the current level
            for (int j = 1; j <= i; j++) {
                // Print the current number and a space
                System.out.print(j + " ");
            }
            // Move to the next line for the next level of the stair
            System.out.println();
        }
    }
}