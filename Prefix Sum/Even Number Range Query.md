### **Even Number Range Query - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Prefix Sum, Range Query

### Problem Statement:
This problem requires handling multiple queries for counting even numbers within different ranges in an array. Each query specifies a range [L, R], and we need to respond with the count of even numbers within that range, inclusive.

### Detailed Explanation:

1. **Understanding the Task:**
   The main challenge here is the multiple queries, each asking for a count of even numbers within a specific range of an array. A naive approach would involve iterating through the specified range for each query, but this would be inefficient with a large number of queries or large arrays.

2. **Optimized Approach using Prefix Sums:**
   To optimize, we use a technique similar to prefix sums. Before handling the queries, we can prepare an auxiliary array that stores the count of even numbers found from the start up to each position of the original array. This preprocessing step enables us to handle each query efficiently.

   For each query [L, R], the count of even numbers is the difference between the counts stored at positions R and L-1 in the auxiliary array. Specifically, the answer is `prefixEven[R] - (L > 0 ? prefixEven[L - 1] : 0)`.

3. **Handling Edge Cases:**
   One edge case to manage is when the range starts at the beginning of the array (L equals 0). Since there's no element before the start, the count at L-1 doesn't exist. We handle this by subtracting zero (effectively ignoring the subtraction) when L is 0.

## Pseudo Code:

```plaintext
Function CalculateEvenCounts:
    Read N, M, A[N]  // Size, queries, and array
    Create prefixEven[N]
    evenCount = 0
    For i from 0 to N-1 do:
        If A[i] % 2 == 0 then:
            evenCount = evenCount + 1
        End If
        prefixEven[i] = evenCount
    End For

    // Handling queries
    For j from 0 to M-1 do:
        Read L, R
        response = prefixEven[R] - (L > 0 ? prefixEven[L - 1] : 0)
        Print response
    End For
End Function
```

### Time Complexity:
The preprocessing of the array takes O(N) time. Each query is handled in O(1) time, so the total time complexity for all queries is O(M). Thus, the overall time complexity is O(N + M).

### Space Complexity:
We are using an auxiliary array of the same size as the input array, so the space complexity is O(N).

## Sample Code (Java):

```java
import java.io.*;
import java.util.*;

public class EvenNumberRangeQuery {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int M = scanner.nextInt();
        int[] array = new int[N];
        int[] prefixEven = new int[N];

        // Constructing the array of prefix counts of even numbers
        int evenCount = 0;
        for (int i = 0; i < N; i++) {
            array[i] = scanner.nextInt();
            if (array[i] % 2 == 0) evenCount++;
            prefixEven[i] = evenCount;
        }

        // Processing each query
        for (int j = 0; j < M; j++) {
            int L = scanner.nextInt();
            int R = scanner.nextInt();
            int response = prefixEven[R] - (L > 0 ? prefixEven[L - 1] : 0);
            System.out.println(response);
        }
    }
}
```

### Conclusion:
This problem showcases an application of the prefix sum technique to optimize range queries. By preprocessing the array, we reduce the time complexity for responding to each query, demonstrating how certain data structures or additional storage can greatly enhance the efficiency of algorithms dealing with repetitive queries.