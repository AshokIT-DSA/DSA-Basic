# Editorial: Uppercase Conversion

## Difficulty: Easy

## Prerequisites
- Strings
- ASCII Values
- Character Manipulation

---

### Problem Statement
You're provided with a string 'S' that consists only of lowercase English letters. Your task is to convert all the characters of 'S' to uppercase without using built-in case conversion methods, and then output the modified string.

---

### Detailed Explanation

1. **Understanding the Task:**
   The task requires converting lowercase letters to uppercase manually, which involves understanding the relationship between characters and their ASCII values. Each lowercase letter can be converted to uppercase by understanding the ASCII difference between lowercase and uppercase letters.

2. **Solution Approach:**
   Instead of using a built-in method to convert the entire string to uppercase, we'll iterate through the characters of the string. For each lowercase character, we'll convert it to its corresponding uppercase character by manipulating the ASCII value. Specifically, we'll subtract 32 (since that's the difference in ASCII values between, for instance, 'a' and 'A') from its ASCII value to get the uppercase version.

3. **Problem Constraints:**
   The maximum length of 'S' is 1000, so iterating over the string and converting it manually won't pose significant performance issues.

---

### Pseudo Code:

<pre><code>
Read the input string 'S'
Initialize an empty string 'result'

for each character 'ch' in 'S':
    Convert 'ch' to its ASCII value and subtract 32 to shift to its uppercase equivalent
    Append the resulting character to 'result'

Print 'result'
</code></pre>

### Complexity Analysis

**Time Complexity:** The time complexity is O(N), where 'N' is the length of the string. We're scanning through each character of the string exactly once.

**Space Complexity:** The space complexity is O(N), where 'N' is the length of the string. We're creating a new string to store the result.

### Sample Code (Java):

```java
import java.util.Scanner;

public class UppercaseConversion {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Read the lowercase string
        String S = scanner.next();
        StringBuilder result = new StringBuilder();

        // Iterate through each character of the string
        for (int i = 0; i < S.length(); i++) {
            // Convert to uppercase by manipulating ASCII value
            char upperCaseChar = (char) (S.charAt(i) - 'a' + 'A');
            result.append(upperCaseChar);
        }

        // Print the converted string
        System.out.println(result.toString());
    }
}
