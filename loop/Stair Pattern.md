### **Stair Pattern - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Nested Loops, Pattern Recognition

### Problem Statement:
Given an integer 'N', your task is to create a stair-like pattern with 'N' steps. Each step's width increases as you go down the levels, forming a right-angled triangular pattern of asterisks.

### Detailed Explanation:

1. **Understanding the Task:**
   We are given a number 'N', and we need to print a pattern that resembles stairs leading upwards, consisting of 'N' steps. The challenge is primarily about understanding nested loop control structures and output formatting.

2. **Solution Approach:**
   The solution requires two loops: an outer loop to handle the number of levels (or 'stairs'), and an inner loop to print the stars '*' that form each level. For each step, the number of stars is equal to the current step number, creating an increasing pattern of stars.

3. **Problem Constraints:**
   The maximum value of 'N' is 100, so the algorithm's performance is not a major concern. We can comfortably use nested loops without running into performance issues.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    for j = 1 to i do:
        print '*', without newline
    end for
    print newline  // Move to the next level of the stair
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2) due to the use of nested loops. Each level i requires printing i stars, and this sum over all levels results in a quadratic number of operations.

### Space Complexity:
O(1), as we're using a constant amount of space, regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class StairPattern {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            // Newline for the next level of stairs
            System.out.println();
        }
    }
}
