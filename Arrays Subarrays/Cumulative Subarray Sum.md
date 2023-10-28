### **Cumulative Subarray Sum - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Mathematical understanding of subarray properties
- Prefix sums

---

### **Problem Statement:**
You are given an array of integers, and your task is to compute the cumulative sum of all possible subarrays. Since the number of subarrays can be large, there is a risk of integer overflow; thus, calculations should be carried out with attention to the data type limits.

---

### **Solution Approach:**

A direct approach would involve generating all possible subarrays and summing their totals. However, this would not be efficient. Instead, we will use a mathematical insight to solve the problem efficiently. 

Every element contributes to several subarrays, and we can determine its total contribution by considering its position in the array and the number of subarrays to which it contributes.

1. **Initialization:**
   - Read the input array.
   - Initialize variables for the total cumulative sum (`totalSum`) and the current subarray sum (`subarraySum`).

2. **Iterative Calculation:**
   - Iterate through each element of the array, calculating its contribution to `subarraySum`. 
   - The contribution of the `i-th` element (`A[i]`) can be determined as `A[i] * (i + 1)` because it will be included in `(i + 1)` subarrays ending at position `i` (considering zero-based indexing).
   - Accumulate this subarray sum in `totalSum`.

3. **Handling Overflow:**
   - Since the problem hints at possible integer overflow, we use `long` data types for our summation variables.

4. **Result Output:**
   - After completing the array's traversal, `totalSum` contains the cumulative sum of all subarrays. Output this value.

### **Pseudo Code:**
```plaintext
Begin
    Read N
    Initialize totalSum = 0, subarraySum = 0
    For i from 0 to N - 1
        Read array element into A[i]
        Calculate subarraySum += A[i] * (i + 1)
        Add subarraySum to totalSum
    End For
    Print totalSum
End
```

### **Time Complexity:**
The algorithm runs with a time complexity of O(N) because it simply involves a single traversal through the array, with constant-time operations performed during each iteration.

### **Space Complexity:**
The space complexity of the algorithm is O(1) (excluding the input space), as it requires only a few auxiliary variables for its calculations.

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Long> A = new ArrayList<>();
        for (int i = 0; i < n; i++) A.add(sc.nextLong());

        long totalSum = 0;
        long subarraySum = 0;

        for (int i = 0; i < n; i++) {
            // Calculate the sum contributed by the current element, taking into account the number of subarrays it will be part of.
            subarraySum += A.get(i) * (i + 1);
            totalSum += subarraySum;
        }

        System.out.println(totalSum);
    }
}
```

---

### **Conclusion:**
This problem emphasizes the importance of recognizing patterns and properties within a dataset to avoid unnecessary computations. By understanding how each element in the array contributes to the final answer, we can calculate the cumulative sum efficiently and avoid the pitfalls of a brute-force approach that would have been computationally expensive.