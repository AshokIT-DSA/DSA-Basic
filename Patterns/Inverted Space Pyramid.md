### **Inverted Space Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Pattern Recognition, Control Structures

### Problem Statement:
Given an integer 'N', the task is to print an inverted pyramid pattern. The pattern comprises 'N' levels, and each level consists of asterisks '*' at the beginning and end, with spaces in between. The number of asterisks increases, and the spaces decrease as you move down the levels.

### Detailed Explanation:

1. **Understanding the Task:**
   We need to create an inverted pyramid that starts with one asterisk on each side and a specific number of spaces in between, based on the input 'N'. As we move down each level, the number of asterisks increases on both sides, and the spaces decrease, creating the inverted pyramid effect.

2. **Solution Approach:**
   The solution involves using nested loops: the outer loop for handling the number of levels and the inner loops for printing the asterisks and spaces. The key is to manage the number of asterisks and spaces correctly as they increase and decrease, respectively, per level.

3. **Problem Constraints:**
   With 'N' up to 100, the algorithm is efficient even with nested loops due to the limited size of the input, avoiding any performance pitfalls.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    // Print leading asterisks
    for j = 1 to i do:
        print '*', without newline
    end for
    // Print spaces
    for j = 1 to 2 * (N - i) do:
        print ' ', without newline
    end for
    // Print trailing asterisks
    for j = 1 to i do:
        print '*', without newline
    end for
    print newline  // Move to the next level of the pyramid
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2) because of the nested loops. Although the number of operations per level isn't constant, the total number of operations is still bounded by a quadratic factor.

### Space Complexity:
O(1), as we don't store the pattern and use only a constant amount of space, irrespective of 'N'.

## Sample Code (Java):

```java
import java.util.Scanner;

public class InvertedSpacePyramid {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            // Printing leading stars
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }

            // Printing spaces
            for (int j = 1; j <= 2 * (N - i); j++) {
                System.out.print(" ");
            }

            // Printing trailing stars
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }

            // Newline for the next level of the pyramid
            System.out.println();
        }
    }
}
