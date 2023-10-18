### **Full Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Nested Loops, Pattern Recognition, Control Structures

### Problem Statement:
Given an integer 'N', your task is to create a full pyramid pattern. The pyramid has 'N' levels, with each level consisting of a sequence of asterisks '*' and spaces. As you go up each level, the number of asterisks increases, forming a pyramid shape.

### Detailed Explanation:

1. **Understanding the Task:**
   We are given a number 'N', and we need to print a pattern that forms a full pyramid. This pattern includes an increasing number of asterisks '*' per level, separated by spaces, and centered in relation to the widest level at the base of the pyramid.

2. **Solution Approach:**
   The solution involves using three loops: 
   - An outer loop to iterate through the 'N' levels.
   - The first inner loop to handle spaces for each level, decreasing as we move up.
   - The second inner loop to handle printing the asterisks, increasing as we move up.
   
   Correctly printing the right number of spaces is crucial to ensuring the asterisks are centered and the pyramid shape is formed.

3. **Problem Constraints:**
   'N' can be as large as 100, ensuring the solution needs to be efficient within this range. The nested looping structure remains practical and won't cause performance issues within this constraint.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    // Print leading spaces for the current level
    for j = 1 to (N - i) do:
        print ' ', without newline
    end for
    // Print asterisks for the current level
    for j = 1 to i do:
        print '*', without newline
        if j < i then
            print ' ', without newline // space between asterisks
        end if
    end for
    print newline  // Move to the next level of the pyramid
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2) due to the nested loops, each running 'N' times. While the inner loops' iterations change per level, the total number of operations doesn't exceed N^2, ensuring the algorithm remains efficient for the given constraints.

### Space Complexity:
O(1), as a constant amount of space is used. The space usage does not depend on the input size 'N', since only a few primitive variables are in use.

## Sample Code (Java):

```java
import java.util.Scanner;

public class FullPyramid {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            // Printing spaces
            for (int j = 1; j <= N - i; j++) {
                System.out.print(" ");
            }

            // Printing asterisks with spaces in between
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
                if (j < i) {
                    System.out.print(" ");
                }
            }

            // Newline for the next level of the pyramid
            System.out.println();
        }
    }
}
