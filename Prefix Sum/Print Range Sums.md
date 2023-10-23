### **Print Range Sums - Editorial**

## Difficulty: Easy

## Prerequisites: Prefix Sum Array, Array Manipulation

### Problem Statement:
This problem requires participants to handle multiple queries asking for the sum of elements in a subarray of a given array 'A'. Each query specifies a range [L, R], and we need to efficiently calculate the sum for this range.

### Detailed Explanation:

1. **Understanding the Task:**
   The problem presents a classic use case for the prefix sum technique because of multiple queries on different index ranges. Computing the sum of each range from scratch for every query would be inefficient, especially with large inputs. A prefix sum array allows us to precompute cumulative sums, enabling faster responses to sum range queries.

2. **Solution Approach:**
   The solution involves creating an auxiliary array, 'prefixSum', where each element is a sum of all previous elements of the original array, 'A'. This approach simplifies finding the sum of any subarray to subtracting two elements of 'prefixSum'.

   - Firstly, we populate 'prefixSum' during a single pass through 'A', keeping a running total of sums.
   - For each query, we calculate the sum for the range [L, R] by subtracting `prefixSum[L - 1]` from `prefixSum[R]`. (If L is 0, we only consider `prefixSum[R]` since there's no previous sum).

   This method allows us to answer each sum query in O(1) time, making it highly efficient for scenarios with numerous queries.

3. **Handling Queries:**
   For every query, the program reads the range's start and end indices, calculates the sum using the 'prefixSum' array, and prints the result. The computation handles the edge case where the starting index is 0.

## Pseudo Code:

```plaintext
Function main:
    Read N, M, A[N]
    Create prefixSum[N]
    Fill prefixSum with cumulative sums of A
    For each query, do:
        Read L, R
        If L > 0, print prefixSum[R] - prefixSum[L - 1]
        Otherwise, print prefixSum[R]
End Function
```

### Time Complexity:
The initial prefix sum array construction requires O(N) time. Each of the M queries is processed in O(1) time, so the total time complexity for handling all queries is O(M). Overall, the algorithm operates in O(N + M) time complexity.

### Space Complexity:
Space complexity is O(N) due to the storage required for the 'prefixSum' array, which is the same size as the input array 'A'.

## Sample Code (Java):

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();
        long[] arr = new long[n];
        long[] prefixSum = new long[n];

        // Constructing the prefix sum array
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextLong();
            prefixSum[i] = (i == 0) ? arr[i] : prefixSum[i - 1] + arr[i];
        }

        // Responding to queries
        for (int i = 0; i < m; i++) {
            int l = sc.nextInt();
            int r = sc.nextInt();
            // Calculate and print the sum of the range
            long sum = prefixSum[r] - ((l > 0) ? prefixSum[l - 1] : 0);
            System.out.println(sum);
        }
    }
}
```

### Conclusion:
This problem highlights the utility of prefix sums in optimizing range sum queries. It underscores the importance of preprocessing in algorithms, significantly enhancing efficiency when dealing with multiple queries or operations on static data sets.