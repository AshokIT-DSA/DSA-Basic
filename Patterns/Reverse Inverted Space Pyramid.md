### **Reverse Inverted Space Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Pattern Recognition, Control Structures

### Problem Statement:
Given an integer 'N', you are required to print a reverse inverted pyramid pattern. The pattern consists of 'N' levels, and each level is composed of a sequence of asterisks '*' and spaces. The number of asterisks decreases, and the spaces increase as you move down the pyramid, which is the reverse of a regular space pyramid.

### Detailed Explanation:

1. **Understanding the Task:**
   We are tasked with creating a reverse inverted pyramid. The pattern starts with the maximum width of asterisks with no spaces in the first row. As we move down each level, the number of asterisks decreases on both sides, and the spaces in between increase, creating the reverse inverted pyramid effect.

2. **Solution Approach:**
   The solution utilizes nested loops: the outer loop for delineating the number of levels and the inner loops for printing the asterisks and spaces. The challenge is in correctly calculating the number of asterisks and spaces per level, ensuring they decrease and increase, respectively, as the levels go down.

3. **Problem Constraints:**
   With 'N' going up to 100, the algorithm will remain efficient even with nested loops, given the input size restrictions. This ensures that performance remains consistent across inputs.

## Pseudo Code:

<pre><code>
read N
for i = N to 1 do:
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
The time complexity is O(N^2) due to the nested loops, each running a maximum of 'N' times. This characteristic ensures that, although the number of operations per level changes, the total number of operations doesn't exceed a quadratic factor.

### Space Complexity:
O(1), as no significant storage is utilized for the pattern, and space usage remains constant regardless of the input 'N'.

## Sample Code (Java):

```java
import java.util.Scanner;

public class ReverseInvertedSpacePyramid {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = N; i >= 1; i--) {
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
