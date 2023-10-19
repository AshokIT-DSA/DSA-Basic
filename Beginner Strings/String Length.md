# Editorial: String Length

## Difficulty: Easy

## Prerequisites
- Strings
- Loops
- Input/Output

---

### Problem Statement
You are tasked with creating a program that first takes an integer 'T' representing the number of test cases. Then, it should accept 'T' strings and output the length of each string on a new line.

---

### Detailed Explanation

1. **Understanding the Task:**
   This problem is straightforward. Your program needs to read an integer 'T', followed by 'T' strings. For each of these strings, your program should compute the string's length and print this length on a new line.

2. **Solution Approach:**
   A simple approach is to use a loop. After reading 'T', you can loop 'T' times, and for each iteration, read a string and use built-in methods or functions to calculate the string's length. Then, immediately print this length.

3. **Problem Constraints:**
   With 'T' being at most 100 and each string's length at most 1000, this approach will not run into performance issues, as modern systems can handle string operations for strings of this size very quickly.

---

### Pseudo Code:

<pre><code>
Read integer 'T'
Loop from 1 to 'T':
    Read string 'S'
    Calculate the length of 'S'
    Print the length of 'S'
End Loop
</code></pre>

### Complexity Analysis

**Time Complexity:** The time complexity for this algorithm is O(N) because the program iterates through all characters of all strings, where 'N' is the total number of characters in all strings.

**Space Complexity:** The space complexity is O(1), as no additional space scaling with the input size is used.

### Sample Code (Java):

```java
import java.util.Scanner;

public class StringLength {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Reading the number of test cases
        int T = scanner.nextInt();
        scanner.nextLine(); // Consuming the leftover newline

        // Iterating through all test cases
        for (int i = 0; i < T; i++) {
            // Reading a string
            String S = scanner.nextLine();
            
            // Printing the length of the string
            System.out.println(S.length());
        }
    }
}