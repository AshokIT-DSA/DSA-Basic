### **Array Prefix Sum - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Prefix Sum

### Problem Statement:
This problem involves computing the prefix sums of an array. The prefix sum is a common technique used in array manipulation, where we are interested in the sum of the elements in a particular range (i, j). Here, we are tasked with modifying the original array such that each element at index 'i' in the array becomes the sum of all elements from index 0 to 'i'.

### Detailed Explanation:

1. **Understanding the Task:**
   The task is straightforward. We have to iterate through the array, and for each position, we accumulate the sum of the elements from the start to the current position. This sum gets stored in the current position, effectively transforming the array into a prefix sum array.

2. **Solution Approach:**
   We can achieve the objective by traversing the array once. We maintain a running sum of the elements encountered, and at each index, we update the element with this running sum. This method ensures that each element reflects the sum of all previous elements, including itself, which is the definition of a prefix sum.

   It's important to note that this process alters the original array. If there's a need to retain the original array data, one should create a separate array for the prefix sums. However, this problem specifies that the transformation should be in place.

3. **Implementation:**
   The implementation doesn't require any complex data structures. The input is an array of integers, and the same array serves as the output with updated values. This in-place transformation ensures minimal space usage and adheres to the problem's constraints.

## Pseudo Code:

```plaintext
Function CalculatePrefixSum:
    Read N, A[N]  // N is the number of elements, A is the array.
    running_sum = 0
    For i from 0 to N-1 do:
        running_sum = running_sum + A[i]
        A[i] = running_sum
    End For
    // The array A now contains the prefix sums.
End Function
```

### Time Complexity:
The algorithm runs in O(N) time since it requires a single pass through the array, where 'N' is the number of elements in the array.

### Space Complexity:
The space complexity is O(1), disregarding the input space, as we're only using a temporary variable to store the running sum and we're updating the original array in place.

## Sample Code (Java):

```java
import java.io.*;
import java.util.*;

public class ArrayPrefixSum {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[] array = new int[N];

        // Reading the array
        for (int i = 0; i < N; i++) {
            array[i] = scanner.nextInt();
        }

        // Calculating the prefix sum in-place
        int runningSum = 0;
        for (int i = 0; i < N; i++) {
            runningSum += array[i];
            array[i] = runningSum;  // Storing the prefix sum back in the array
        }

        // Output the array after the prefix sum calculation
        for (int value : array) {
            System.out.print(value + " ");
        }
    }
}
```

### Conclusion:
This problem serves as an excellent introduction to the concept of prefix sums, a technique vital in competitive programming, particularly in problems involving queries about subarrays. The task demonstrates the efficiency of prefix sums in reducing time complexity for range sum queries in arrays.