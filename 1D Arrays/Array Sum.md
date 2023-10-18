# Array Sum - Editorial

## Problem Analysis:
The "Array Sum" problem requires you to calculate the sum of all elements in a given array 'A' of size 'N'. It's a straightforward problem focusing on array traversal and accumulation of values.

## Prerequisites:
- Arrays
- Looping (iteration)

## Problem Statement:
Given an array 'A' consisting of 'N' elements, the task is to find and print the sum of the elements of the array.

## Constraints:
- The size 'N' of the array is at most 1000, ensuring the operation can be efficiently performed within a reasonable time frame on most hardware.
- Individual elements 'A[i]' have a maximum value of 10000, preventing integer overflow under reasonable summation cases, given the array size constraint.

## Solution Approach:
A simple approach to solving this problem is by using a loop to traverse the array while maintaining a running total of the array elements.

1. Initialize a variable 'sum' to 0; this variable will store the total sum of array elements.
2. Iterate through each element of the array (from the first to the last element).
3. For each element, add its value to 'sum'.
4. After completing the loop, 'sum' contains the total sum of the array's elements, which you then print or return.

## Pseudo Code:

<pre><code>
read N
read array A of size N
initialize sum as 0
for i = 0 to N - 1 do
    sum = sum + A[i]
end for
print sum
</code></pre>

## Time Complexity:
O(N), where 'N' is the number of elements in the array 'A'. This is because we traverse the entire array once, performing a constant-time operation for each element.

## Space Complexity:
O(1), as we are using a constant amount of space (the variable 'sum' and counter 'i') besides the input array itself.

## Sample Code in Java:

```java
import java.util.Scanner;

public class ArraySum {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Step 1: Read the size of the array
        int N = scanner.nextInt();
        int[] A = new int[N];

        // Step 2: Read the elements of the array
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        // Step 3: Calculate the sum of the array
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += A[i];
        }

        // Step 4: Print the sum
        System.out.println(sum);
    }
}
