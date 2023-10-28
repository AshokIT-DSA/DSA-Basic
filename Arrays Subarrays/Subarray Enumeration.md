### **Subarray Enumeration - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Understanding of subarrays

---

### **Problem Statement:**
The task requires enumerating all possible subarrays of a given array. A subarray is a contiguous part of an array obtained by selecting elements from a continuous sequence. Each subarray needs to be printed on a new line.

---

### **Solution Approach:**

To solve this problem, we will use a nested loop. The first loop marks the starting point of a subarray, and the second loop defines the end point. By iterating over all possible starting and ending points, we cover all subarrays.

1. **Initialization:**
   - Read the array's size and elements.

2. **Enumeration of Subarrays:**
   - The outer loop runs from the first element to the last. This loop represents the starting point of the subarray.
   - The inner loop runs from the current element of the outer loop to the end of the array. This loop represents the ending point of the subarray.
   - For each iteration of the inner loop, we print a subarray that starts and ends at the indices pointed by the outer and inner loops, respectively.

### **Algorithm Steps:**
```plaintext
Begin
    Read N
    Read array A of size N
    For i from 0 to N-1
        For j from i to N-1
            For k from i to j
                Print A[k]
            EndFor
            Print newline
        EndFor
    EndFor
End
```

### **Time Complexity:**
The algorithm involves three nested loops running from 0 to N, resulting in a time complexity of O(N^3). This cubic time complexity is acceptable because the problem's constraints limit N to a maximum of 100, ensuring the program's execution within a reasonable time.

### **Space Complexity:**
The space complexity of the algorithm is O(1), as it doesn’t require any extra space proportional to the input's size (other than the input space itself).

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        // Scanner object for taking input
        Scanner sc = new Scanner(System.in);
        
        // Read the number of elements
        int N = sc.nextInt();
        
        // Array to store the numbers
        int[] array = new int[N];
        for (int i = 0; i < N; i++) {
            array[i] = sc.nextInt();
        }

        // Generate and print all subarrays
        for (int i = 0; i < N; i++) {
            for (int j = i; j < N; j++) {
                // Print subarray from i to j
                for (int k = i; k <= j; k++) {
                    System.out.print(array[k] + " ");
                }
                System.out.println();
            }
        }
    }
}
```

---

### **Conclusion:**
This problem is straightforward but illustrates fundamental concepts in working with arrays and nested loops. By printing all subarrays, we gain a deeper understanding of the structure of arrays and the nature of subarrays. Although the approach is not efficient for large inputs, it sufficiently solves the problem within the given constraints.