# Editorial: Max Character Type Count

## Difficulty: Easy

## Prerequisites
- Strings
- Counting
- Conditions

---

### Problem Statement
Your program needs to analyze a string 'S', composed of alphabets ('a' to 'z' and 'A' to 'Z') and digits ('0' to '9'). The objective is to determine which type of characters occur more frequently in the string and print the count of that character type.

---

### Detailed Explanation

1. **Understanding the Task:**
   This problem requires you to check each character of the input string and categorize it as either an alphabet or a digit. You must then compare the totals for each category to determine which has the higher count and print that count.

2. **Solution Approach:**
   To solve this problem, you can iterate through each character of the string, checking whether it's an alphabet or a digit, and increment the corresponding count. After checking all characters, compare the two counts and print the larger one. 

   The key methods needed for this approach are character checking methods, loop structures for iteration, and if-else conditions for comparisons.

3. **Problem Constraints:**
   The constraints indicate that the string length can be as much as 10<sup>5</sup>. This fact suggests that the algorithm should avoid excessive complexity. The proposed method operates with linear complexity, making it suitable given the constraints.

---

### Pseudo Code:

<pre><code>
Read the string 'S'
Set 'alphabetCount' to 0
Set 'digitCount' to 0

For each character 'ch' in 'S':
    If 'ch' is an alphabet:
        Increment 'alphabetCount'
    Else if 'ch' is a digit:
        Increment 'digitCount'
    End If
End For

If 'alphabetCount' > 'digitCount':
    Print 'alphabetCount'
Else:
    Print 'digitCount'
End If
</code></pre>

### Complexity Analysis

**Time Complexity:** The time complexity for this algorithm is O(N), as the algorithm needs to iterate through each character of the input string, where 'N' is the length of the string.

**Space Complexity:** The space complexity is O(1), since we are using a constant space for the counters regardless of the input size.

### Sample Code (Java):

```java
import java.util.Scanner;

public class MaxCharacterTypeCount {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String S = scanner.next();

        int alphabetCount = 0, digitCount = 0;

        for (char ch : S.toCharArray()) {
            if (Character.isLetter(ch)) {
                alphabetCount++;
            } else if (Character.isDigit(ch)) {
                digitCount++;
            }
        }

        System.out.println(Math.max(alphabetCount, digitCount));
    }
}
