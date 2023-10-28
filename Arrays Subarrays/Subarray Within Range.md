### **Subarray Within Range - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Iteration

---

### **Problem Statement:**
This problem necessitates that the participant extracts elements of a subarray from the original array 'A' within the index range 'X' to 'Y' (inclusive). The challenge involves both understanding array indexing (0-based) and implementing a solution that efficiently navigates array elements within specified boundaries.

---

### **Solution Approach:**
The solution method is straightforward and involves a single pass through the array 'A' while extracting the elements that fall within the index range 'X' to 'Y'. 

Here’s a step-by-step approach:

1. **Reading Inputs:**
   - Read the total number of elements (N) in the array.
   - Read the range limits 'X' and 'Y'.
   - Validate that 'X' and 'Y' satisfy the constraint (1 <= X <= Y <= N - 1).

2. **Iterative Element Extraction:**
   - Iterate through the array, and for each element, if the current index falls within 'X' and 'Y', print the element. This step requires understanding that array indexing is 0-based, so the actual elements correspond to indices 'X' to 'Y'.

3. **Output:**
   - The program prints the relevant elements as they are found, separated by a space. There is no need to store these elements as they can be printed directly during the iteration process.

### **Pseudo Code:**
```plaintext
Begin
    Read integer N
    Read integers X, Y
    Initialize counter i to 0
    While i < N
        Read next element of the array, val
        If i is within the range X to Y
            Print val with a trailing space
        End If
        Increment i
    End While
End
```

### **Time Complexity:**
The time complexity of the solution is O(N), where 'N' is the number of elements in the array. This is because the algorithm iterates through each element of the array exactly once.

### **Space Complexity:**
The algorithm’s space complexity is O(1) because it does not use any additional storage structures that grow with the input size. It directly reads and processes each element of the array, printing qualifying elements on the go.

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int x = sc.nextInt();
        int y = sc.nextInt();
        for (int i = 0; i < n; i++) {
            int val = sc.nextInt();
            if (i >= x && i <= y) System.out.print(val + " ");
        }
    }
}
```

---

### **Conclusion:**
The problem is designed to test the participant's understanding of array traversal and conditional extraction based on index positions. By directly processing the inputs and conditionally printing the necessary elements, the solution avoids unnecessary storage and operations, thereby adhering to optimal time and space usage constraints.