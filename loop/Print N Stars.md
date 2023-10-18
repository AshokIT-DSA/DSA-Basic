### **Print N Stars - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, String Manipulation

### Problem Statement:
Your task is straightforward. Given an integer 'N,' you need to print a line of 'N' stars. The challenge might seem trivial but it's an excellent step for beginners to understand basic output formatting and loops.

### Detailed Explanation:

1. **Understanding the Task:**
   You're given a number 'N', and your sole job is to print 'N' stars (*) on one line. It doesn't involve any complicated logic, making it perfect for beginners to practice their coding skills.

2. **Solution Approach:**
   This problem can be solved by using a simple loop that runs 'N' times, and each time it iterates, a star is printed on the screen without a newline character at the end. Hence, all stars are printed on the same line.

3. **Problem Constraints:**
   Since 'N' can be at most 100, performance isn't a concern here, and the solution can be implemented efficiently without worrying about the system's processing time.

## Pseudo Code:

<pre><code>
read N
for i = 1 to N do:
    print '*', without newline
end for
print newline  // so that the output ends with a newline character
</code></pre>

### Time Complexity:
The time complexity is O(N) because there's a single loop that runs 'N' times.

### Space Complexity:
O(1), as we're using a constant amount of space regardless of the size of the input.

## Sample Code (Java):

```java
import java.util.Scanner;

public class PrintNStars {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();

        for (int i = 0; i < N; i++) {
            System.out.print("*");
        }
        // Newline for end of output, for formatting purposes
        System.out.println();
    }
}
