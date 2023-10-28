### **Maximum Subarray Sum Threshold - Editorial**

---

## **Difficulty: Medium**

---

## **Prerequisites:**
- Arrays
- Sliding Window
- Prefix Sum

---

### **Problem Statement:**
This task requires finding the maximum possible sum of any subarray within array 'A' such that the sum does not exceed a specified limit 'B'. The challenge lies in efficiently identifying the subarray that meets this criterion without having to compare the sums of all possible subarrays explicitly.

---

### **Solution Approach:**
The solution employs a 'sliding window' technique that dynamically adjusts the range of the current subarray being considered based on its sum relative to the limit 'B'.

Outlined below are the steps:

1. **Initialization:**
   - Read the input array and the limit 'B'.
   - Initialize variables to track the maximum sum found ('max'), the current sum of the subarray ('sum'), and the 'start' index of the current subarray.

2. **Iterative Calculation:**
   - Iterate through the array, extending the current subarray by including each new element in 'sum'.
   - Whenever 'sum' exceeds 'B', shrink the window from the left by incrementing 'start' and subtracting the corresponding element from 'sum' until 'sum' is less than or equal to 'B'.
   - Update 'max' with the higher value between the current 'max' and 'sum' after each iteration.

3. **Result Output:**
   - After completing the array's traversal, 'max' contains the maximum sum that does not exceed 'B'. Output this value.

### **Pseudo Code:**
```plaintext
Begin
    Read N, B
    Initialize max = 0, sum = 0, start = 0
    For i from 0 to N - 1
        Read array element into arr[i]
        Add arr[i] to sum
        While sum > B and start < N
            Subtract arr[start] from sum
            Increment start
        End While
        Set max to the maximum of max and sum
    End For
    Print max
End
```

### **Time Complexity:**
The time complexity is O(N), where 'N' is the number of elements in the array. This is because each element is added once and removed at most once. The operation of calculating the sum is done in constant time.

### **Space Complexity:**
The algorithm runs with a space complexity of O(1), aside from the input storage, as it only requires a few auxiliary variables, regardless of the input size.

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int b = sc.nextInt();
        int arr[] = new int[n];
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();
        
        int max = 0;
        int sum = 0;
        int start = 0;
        for (int i = 0; i < n; i++) {
            sum += arr[i];
            while (sum > b && start < n) {
                sum -= arr[start];
                start++;
            }
            max = Math.max(sum, max);
        }
        System.out.println(max);
    }
}
```

---

### **Conclusion:**
The problem assesses understanding of efficient array traversal using the sliding window technique. It's essential to avoid a brute force approach that would have significantly higher complexity. The solution maintains optimal time efficiency by adjusting the subarray range dynamically and ensures we do not exceed the threshold, thereby maintaining the constraint conditions.