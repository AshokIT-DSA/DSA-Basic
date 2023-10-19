# Editorial: Last Occurrence

## Difficulty: Easy

## Prerequisites
- Strings
- ASCII
- Linear Search (Reverse)

---

### Problem Statement
You are given a string 'S' consisting of lowercase English letters and an integer 'B' representing an ASCII code. Your task is to find the position of the last (rightmost) occurrence of any character in 'S' whose ASCII code is 'B'. If there is no such character, the program should return -1.

---

### Detailed Explanation

1. **Understanding the Task:**
   You need to inspect each character of 'S', check its ASCII code, and compare it with 'B'. Your goal is to find the last character in 'S' that matches 'B' in terms of ASCII code. If you find a match, you should return its position (index) in 'S'; otherwise, you should return -1.

2. **Solution Approach:**
   The solution involves iterating through the string 'S' in reverse (from end to start) and checking the ASCII value of each character. This can be achieved using a simple loop and a character-to-ASCII conversion for the comparison. As soon as we find a character that meets the criteria, we break the loop and return the index.

3. **Problem Constraints:**
   With the maximum length of 'S' being up to 10<sup>5</sup> and the range of 'B' (97 to 122), our approach needs to efficiently handle potentially large strings. Since we're performing a single pass through 'S', our algorithm will have a linear time complexity.

---

### Pseudo Code:

<pre><code>
Read the string 'S'
Read the integer 'B'
Set 'foundIndex' to -1

For 'index' from (length of 'S' - 1) down to 0:
    If ASCII value of 'S' at 'index' is equal to 'B':
        Set 'foundIndex' to 'index'
        Break the loop
    End If
End For

Print 'foundIndex'
</code></pre>

### Complexity Analysis

**Time Complexity:** The time complexity is O(N), where 'N' is the length of the string 'S'. In the worst case, we traverse the entire string to find the last occurrence of the character with ASCII value 'B'.

**Space Complexity:** The space complexity is O(1), as we are using a constant amount of space and not storing any additional characters from the string.

### Sample Code (Java):

```java
import java.util.Scanner;

public class LastOccurrence {

    public static void main(String[] args) {
        Scanner scanner = a Scanner(System.in);
        String S = scanner.next();
        int B = scanner.nextInt();

        int foundIndex = -1;

        // Loop through the string in reverse
        for (int index = S.length() - 1; index >= 0; index--) {
            if ((int) S.charAt(index) == B) {
                foundIndex = index;
                break;
            }
        }

        System.out.println(foundIndex);
    }
}