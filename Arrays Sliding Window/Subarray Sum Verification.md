### **Subarray Sum Verification - Editorial**

---

## **Difficulty: Easy-Medium**

---

## **Prerequisites:**
- Arrays
- Sliding Window Technique

---

### **Problem:**
The task is to determine if there exists a subarray of a given length (B) within an array such that the sum of its elements is equal to a given number (C).

---

### **Approach:**
The problem can be solved efficiently using the **sliding window technique**. Here's how you can use the sliding window approach:

1. Compute the sum of the first `B` elements. 
2. If this sum is equal to `C`, then return true.
3. If not, start a loop from `B` to the end of the array:
    1. Subtract the first element of the previous window and add the current element to maintain a continuous sum of `B` elements.
    2. After every addition, check if the new sum is equal to `C`.
    3. If it ever matches, return true.
4. If we have checked the entire array and haven't found a subarray with a sum equal to `C`, return false.

### **Why does this work?**
This approach works because we are essentially moving a fixed-size window (of size `B`) over the array while maintaining the sum of elements inside this window. By updating our sum in constant time (subtracting the leftmost element and adding the rightmost element), we can efficiently check the condition for each window in the array without having to recalculate the sum from scratch.

### **Algorithm:**
```plaintext
Begin
    Read N, B, C and the array A

    Initialize sum as the sum of the first B elements of A
    If sum equals C, return true

    For i from B to end of A:
        Update sum by subtracting A[i-B] and adding A[i]
        If sum equals C, return true
    EndFor

    If no such subarray is found, return false
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N)
  - We are essentially iterating over the array only once, making the time complexity linear or O(N).

- **Space Complexity:** O(1)
  - The solution doesn't use any additional space proportional to the size of the input, so the space complexity is O(1).

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();
        int[] arr = new int[n];
        for(int i=0;i<n;i++) arr[i] = sc.nextInt();
        
        System.out.println(solve(arr,b,c));
    }
    
    public static boolean solve(int[] A, int B, int C) {
        int sum = 0;
        
        // Compute the sum of the first B elements
        for(int i=0;i<B;i++) sum += A[i];
        
        // Check if the sum matches C
        if(sum == C) return true;

        // Slide the window over the array and check
        for(int i=B;i<A.length;i++) {
            sum = (sum-A[i-B])+A[i];
            if(sum == C) return true;
        }
        
        // If no matching subarray is found
        return false;
    }
}
```

---

### **Conclusion:**
The sliding window technique is a powerful approach for solving problems that require checking or computing something over a fixed-length segment or subarray of an array. This problem showcases the basic usage of the sliding window technique and can be a good starting point for beginners.