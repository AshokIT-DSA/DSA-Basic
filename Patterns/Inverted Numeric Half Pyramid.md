### **Inverted Numeric Half Pyramid - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Pattern Recognition, Control Structures

### Problem Statement:
Given an integer 'N', you are required to print an inverted half pyramid with 'N' levels using numbers. The pyramid starts with numbers from 1 to 'N' and reduces one number from the end as we move to the next level.

### Detailed Explanation:

1. **Understanding the Task:**
   We need to print an inverted half pyramid pattern using numbers, with 'N' specifying the number of levels and the range of numbers on the topmost level. Each subsequent level loses the last number from the end, creating an effect of the pyramid narrowing down.

2. **Solution Approach:**
   We require two loops: an outer loop to iterate through the levels of the pyramid, and an inner loop to print the numbers on each level. We start from 'N' numbers, and as we go down one level, the range of numbers decreases by one.

3. **Problem Constraints:**
   'N' can be as large as 100, ensuring that performance issues will not arise, thereby making nested loops a viable solution without risking inefficiency.

## Pseudo Code:

<pre><code>
read N
for i = N down to 1 do:
    for j = 1 to i do:
        print j, without newline
        if j < i, print ' ', without newline // space between numbers
    end for
    print newline  // Move to the next level of the pyramid
end for
</code></pre>

### Time Complexity:
The time complexity is O(N^2) due to the nested loops. The inner loop's iterations decrease with each pass, but the sum total of operations still constitutes a quadratic number of operations.

### Space Complexity:
O(1), since we are using a fixed amount of space and not storing the pyramid structure. The variables used do not scale with the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class InvertedNumericHalfPyramid {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = N; i >= 1; i--) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j);
                if (j < i) {
                    System.out.print(" ");  // Print space between numbers
                }
            }
            // Newline for the next level of the pyramid
            System.out.println();
        }
    }
}
