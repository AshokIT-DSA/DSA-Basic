### **Leading Spaces Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Nested Loops, Pattern Recognition, String Manipulation

### Problem Statement:
Given an integer 'N', your task is to create a pyramid-like pattern with 'N' levels. Each level of the pyramid should be centered, with the number of asterisks on each level corresponding to the level number. The pyramid should be right-justified.

### Detailed Explanation:

1. **Understanding the Task:**
   We are given a number 'N', representing the total number of levels in a pyramid. The pattern must be printed with spaces leading on each line so that the asterisks forming the pyramid are centered. Understanding nested loop control structures and string manipulation (for handling spaces) is crucial here.

2. **Solution Approach:**
   The solution requires three loops: one outer loop to handle the number of levels in the pyramid, a second loop to print the required spaces on each level, and a third loop to print the asterisks. The key is to decrease the number of spaces while increasing the number of asterisks as we move down the pyramid levels.

3. **Problem Constraints:**
   With 'N' having a maximum value of 100, performance issues related to the algorithm aren't a concern. This allows us to use nested loops conveniently for pattern generation.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    // Print leading spaces for the current level
    for j = 1 to N - i do:
        print ' ', without newline
    end for
    // Print asterisks for the current level
    for j = 1 to i do:
        print '*', without newline
    end for
    print newline  // Move to the next level of the pyramid
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2) because of the nested loops. While one sequence of loops prints spaces, another sequence prints stars, each running based on 'N', resulting in a quadratic number of operations.

### Space Complexity:
O(1), as we are not using any additional space that scales with input size. The space used for the input and the temporary variables is constant regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class LeadingSpacesPyramid {
    public static main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            // Print leading spaces
            for (int j = 1; j <= N - i; j++) {
                System.out.print(" ");
            }
            // Print asterisks for the current level
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            // Newline for the next level of the pyramid
            System.out.println();
        }
    }
}
