### **Counting Subsequence - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Strings
- Iteration

---

### **Problem Statement:**
You are given a string S, consisting of uppercase English letters. Your task is to find and count how many times the subsequence "AB" appears in the string.

---

### **Solution Approach:**
The solution uses a straightforward approach by directly scanning the string for occurrences of "AB". Here’s how it is achieved:

1. **Reading the Input:**
   - The string S is read from the standard input.

2. **Initialization:**
   - An integer variable 'c' is initialized to 0. This variable will hold the count of occurrences of "AB".

3. **Linear Scan:**
   - The string is traversed using a 'for' loop from the start to the second-to-last character. We don't need to check the last character since it cannot start an "AB" sequence.
   - Within each iteration, we check if the current character and the next one in the sequence form the string "AB".
   - If they do, we increment the count 'c'.

4. **Result Output:**
   - After the loop, we've counted all "AB" occurrences in the string. The final step is to print this count to the standard output.

The beauty of this solution lies in its simplicity and directness. However, it operates under the assumption that we're interested in "AB" as a direct subsequence (consecutive characters) rather than a general subsequence.

### **Pseudo Code:**
```plaintext
Begin
    Read the string S
    Initialize count 'c' to 0
    For i = 0 to length of S - 2
        If S[i] is 'A' and S[i+1] is 'B' Then
            Increment 'c'
        End If
    End For
    Print 'c'
End
```

### **Time Complexity:**
The algorithm runs in O(N) time complexity, where N is the length of the string. This is because it makes a single pass through the string, checking each character exactly once.

### **Space Complexity:**
The space complexity is O(1), as the storage used does not increase with the size of the input string.

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
        int c = 0;
        for(int i=0; i<str.length()-1; i++) {
            if(str.charAt(i) == 'A' && str.charAt(i+1) == 'B') c++;
        }
        System.out.println(c);
    }
}
```

---

### **Conclusion:**
This problem tests the basic understanding of string manipulation and iteration. The solution efficiently handles the task by performing a single linear scan of the string and checking for consecutive 'A' and 'B' characters, thus maintaining an optimal time complexity.