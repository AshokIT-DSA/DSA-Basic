# Search Element - Editorial

## Problem Analysis:
This task requires participants to search for an element within an array. It tests basic understanding of array manipulation and search algorithms.

## Prerequisites:
- Arrays
- Iteration (looping)
- Condition checking

## Problem Statement:
For each test case, participants are given an array 'A' and a target integer 'X'. They must determine whether 'X' is present in 'A'.

## Constraints:
- 1 <= T <= 100
- 1 <= N <= 10<sup>5</sup>
- 1 <= A[i], X <= 10<sup>9</sup>

The constraints are set to ensure the problem doesn't require complex optimizations. Given the maximum size of 'N', a linear search is sufficient without exceeding time limits.

## Solution Approach:
The simplest approach is using a linear search, where we go through each element in the array 'A' and compare it with 'X'. If a match is found, we return a positive result. If we get through the array without finding 'X', we return a negative result.

1. Loop through each test case 'T'.
2. For each test case, read 'N' (the number of elements) and 'X' (the target element).
3. Initialize a boolean flag as false (indicating 'X' is not found).
4. Read the array elements.
5. Traverse the array:
   - If any element matches 'X', set the flag as true and break out of the loop.
6. After the loop, check the flag. If true, print positive result; otherwise, print negative result.

## Pseudo Code:

<pre><code>
read T
while T > 0 do
    read N, X
    read array A of size N
    set flag = false
    for i = 0 to N-1 do
        if A[i] == X then
            set flag = true
            break
        end if
    end for
    if flag is true then
        print "Yes"
    else
        print "No"
    end if
    decrement T
end while
</code></pre>

## Time Complexity:
O(N), where 'N' is the number of elements in the array. The solution involves a single traversal through the array.

## Space Complexity:
O(1), as no additional space that scales with input size is being used. We are only using space for primitive variables, regardless of the input size.

## Sample Code in Java:

```java
import java.util.Scanner;

public class SearchElement {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();

        while (T-- > 0) {
            int N = scanner.nextInt();
            int X = scanner.nextInt();
            boolean found = false;

            // Read array and search for X
            for (int i = 0; i < N; i++) {
                int current = scanner.nextInt();
                if (current == X) {
                    found = true;
                    break;
                }
            }

            // Output result
            if (found) {
                System.out.println("Yes");
            } else {
                System.out.println("No");
            }
        }
    }
}
