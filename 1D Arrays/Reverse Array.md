# Reverse Array - Editorial

## Problem Analysis:
This task requires reversing the elements of an array. This simple operation is fundamental to understanding array manipulation and in-place array modifications.

## Prerequisites:
- Arrays
- Looping (iteration)

## Problem Statement:
Given an array 'A' of size 'N', your task is to reverse the array elements and print the reversed array.

## Constraints:
- 1 <= N <= 1000
- 1 <= A[i] <= 10000

The constraints ensure the array has at most 1000 elements, meaning a straightforward solution will not exceed time limits. The elements in the array are reasonably limited in size to avoid integer overflow.

## Solution Approach:
The solution involves swapping the elements of the array. Specifically, the element at the first position is swapped with the element at the last, the element at the second position with the element at the second last, and so on, until the array is reversed.

1. Initialize two pointers (or indices): 'start' at 0 and 'end' at N-1.
2. While 'start' is less than 'end':
   - Swap the elements at 'start' and 'end'.
   - Increment 'start'.
   - Decrement 'end'.
3. The array is now reversed.

This approach doesn't require any additional space and preserves the original order of the array elements in the reversed array.

## Pseudo Code:

<pre><code>
read N
read array A of size N
initialize start = 0
initialize end = N - 1
while start < end do
    swap A[start] with A[end]
    increment start
    decrement end
end while
print array A
</code></pre>

## Time Complexity:
O(N), where 'N' is the number of elements in the array. This is because we're traversing only half of the array thanks to the two-pointer technique, but simplifying the notation removes constants, resulting in O(N).

## Space Complexity:
O(1), as we are using a constant amount of space. The array is reversed in place, and no additional data structures are used.

## Sample Code in Java:

```java
import java.util.Scanner;

public class ReverseArray {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Read the size of the array
        int N = scanner.nextInt();
        int[] A = new int[N];
        
        // Read the elements of the array
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        // Initialize start and end pointers
        int start = 0;
        int end = N - 1;

        // Reverse the array
        while (start < end) {
            // Swap the elements
            int temp = A[start];
            A[start] = A[end];
            A[end] = temp;

            // Move the pointers
            start++;
            end--;
        }

        // Print the reversed array
        for (int i = 0; i < N; i++) {
            System.out.print(A[i] + " ");
        }
    }
}
