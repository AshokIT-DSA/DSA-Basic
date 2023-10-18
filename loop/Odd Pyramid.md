### **Odd Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: 
- Loops
- Nested Loops
- Pattern Recognition
- Conditional Logic

### Problem Statement:
Given an integer 'N', you are required to print a pattern that aligns with 'N'. The pattern consists of odd numbers and spaces, forming a pyramid shape. The numbers increase in odd increments (e.g., 1, 3, 5) as you descend the levels.

### Detailed Explanation:

1. **Understanding the Task:**
   The problem involves printing patterns, a common theme in many introductory programming exercises. Here, the twist is incorporating not just any sequence of numbers but specifically the odd sequence within a structured pattern, ensuring the correct spacing to maintain the pyramid's structure.

2. **Solution Approach:**
   The approach requires a loop mechanism to control the number of levels in the pyramid (outer loop), and within each level, conditional printing must be managed: printing an odd number or a space based on the current position (inner loop). The trick is to identify when to print a number and when to print a space, maintaining the alignment.

3. **Problem Constraints:**
   With 'N' having a maximum of 100, performance is not a significant concern, allowing a straightforward solution using nested loops without worrying about efficiency losses in this context.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    number = 1
    for j = 1 to i do:
        if number <= N then:
            print number, without newline
            print ' ', without newline // space after the number
            number = number + 2 // move to the next odd number
        end if
    end for
    print newline  // Move to the next level of the pyramid
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2), influenced by nested loops running for 'N' levels, and operations within each level that are also proportional to 'N'.

### Space Complexity:
O(1), as the space used (variables for loops and logic) does not scale with input size 'N'.

## Sample Code (Java):

```java
import java.util.Scanner;

public class OddPyramid {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            int number = 1;  // Initialize the first number
            for (int j = 1; j <= i; j++) {
                if (number <= N) {
                    System.out.print(number + " ");  // Print the current odd number and a space
                    number += 2;  // Increment to the next odd number
                }
            }
            System.out.println();  // Move to the next line for the new level of the pyramid
        }
    }
}
