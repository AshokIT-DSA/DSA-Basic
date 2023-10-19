# Check Palindrome - Editorial

## Difficulty: Easy

## Prerequisites: Strings, Looping, Conditions

### Problem Statement
You're tasked with writing a program to determine whether a given string is a palindrome. The program should return `True` if the string is a palindrome and `False` otherwise. A palindrome is defined as a string that reads the same backward as forward.

### Detailed Explanation

1. **Understanding the Task:**
   This task requires you to verify whether a provided string is a palindrome. Essentially, you'll need to compare characters in the string symmetrically from the outside working inwards, checking if the string reads the same in both directions.

2. **Solution Approach:**
   The most straightforward way to solve this problem is by using a two-pointer technique. This approach involves:
   - Setting one pointer at the start (left) and one at the end (right) of the string.
   - Moving both pointers towards the center of the string, comparing the characters at the current positions.
   - If the characters are different, the string is not a palindrome.
   - If the pointers meet in the middle and all characters have matched so far, the string is a palindrome.

3. **Problem Constraints:**
   Given the maximum number of test cases (t) is 10, performance issues are minimal with this approach, and we can efficiently perform string comparisons.

### Pseudo Code:

<pre><code>
Function isPalindrome(string: s)
    Set left to 0
    Set right to length of s - 1

    While left is less than right
        If character at s[left] is not equal to s[right]
            Return False
        End If
        Increase left by 1
        Decrease right by 1
    End While

    Return True  // If the whole string has been checked without discrepancies.
End Function
</code></pre>

### Time Complexity:
The time complexity for this algorithm is O(N), where 'N' is the number of characters in the string. This is because, in the worst case, each character in the string is compared once.

### Space Complexity:
The space complexity is O(1), as we are not utilizing any additional space that scales with the input size. The variables used for the pointers (`left` and `right`) do not depend on the input size.

### Sample Code (Java):

```java
public class CheckPalindrome {

    public static boolean isPalindrome(String s) {
        int left = 0, right = s.length() - 1;

        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }

        return true;
    }

    public static void main(String[] args) {
        // Example usage
        String stringInput = "madam";
        System.out.println(isPalindrome(stringInput));
        // Output: true
    }
}