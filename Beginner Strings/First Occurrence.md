# Editorial: First Occurrence

## Difficulty: Easy

## Prerequisites
- Strings
- ASCII
- Linear Search

---

### Problem Statement
You are given a string 'S' consisting of lowercase English letters and an integer 'B' representing an ASCII code. Your task is to find the position of the first occurrence of any character in 'S' whose ASCII code is 'B'. If there is no such character, the program should return -1.

---

### Detailed Explanation

1. **Understanding the Task:**
   You need to inspect each character of 'S', check its ASCII code, and compare it with 'B'. You are looking for the first character that matches 'B' in terms of ASCII code. If you find a match, you should return its position (index) in 'S'; otherwise, you should return -1.

2. **Solution Approach:**
   The solution involves iterating through the string 'S' and checking the ASCII value of each character. This can be achieved using a simple loop and a character-to-ASCII conversion for the comparison. As soon as we find a character that meets the criteria, we break the loop and return the index.

3. **Problem Constraints:**
   Given the maximum length of 'S' (up to 10<sup>5</sup>) and the range of 'B' (97 to 122), our approach needs to handle large strings efficiently. However, since we're performing a single pass through 'S', our algorithm will have a linear time complexity.

---

### Pseudo Code:

<pre><code>
Read the string 'S'
Read the integer 'B'
Set 'foundIndex' to -1

For 'index' from 0 to length of 'S' - 1:
    If ASCII value of 'S' at 'index' is equal to 'B':
        Set 'foundIndex' to 'index'
        Break the loop
    End If
End For

Print 'foundIndex'
</code></pre>

### Complexity Analysis

**Time Complexity:** The time complexity is O(N), where 'N' is the length of the string 'S'. In the worst case, we traverse the entire string to find the first occurrence of the character with ASCII value 'B'.

**Space Complexity:** The space complexity is O(1), as we are using a constant amount of space and not storing any additional characters from the string.

### Sample Code (Java):

```java
import java.util.Scanner;

public class FirstOccurrence {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String S = scanner.next();
        int B = scanner.nextInt();

        int foundIndex = -1;

        for (int index = 0; index < S.length(); index++) {
            if ((int) S.charAt(index) == B) {
                foundIndex = index;
                break;
            }
        }

        System.out.println(foundIndex);
    }
}
