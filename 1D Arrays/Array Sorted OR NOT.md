# Array Sorted OR NOT - Editorial

## Problem Analysis:
This problem requires the participants to check if a given array is sorted. The sorting can be in either ascending or descending order. The challenge lies in understanding that the array does not need to be sorted in one particular order.

## Prerequisites:
- Arrays
- Iteration (looping)
- Basic understanding of sorting

## Problem Statement:
Participants are given an array 'A' of 'N' elements. They need to determine whether the array is sorted in either ascending or descending order.

## Constraints:
- 1 <= N <= 1000
- 1 <= A[i] <= 10<sup>5</sup>

These constraints indicate that the problem can be solved using simple iteration without exceeding time limits.

## Solution Approach:
The solution involves a single traversal through the array. We need to check two conditions - if the array is in ascending order or in descending order.

1. Initialize two boolean variables, `isAscending` and `isDescending`, as true.
2. Loop through the array from the second element to the end.
3. For each element, check:
   - If the current element is smaller than the previous, set `isAscending` to false.
   - If the current element is larger than the previous, set `isDescending` to false.
4. If either `isAscending` or `isDescending` remains true, the array is sorted. Otherwise, it's not sorted.

## Pseudo Code:

<pre><code>
read N
read array A of size N
set isAscending = true
set isDescending = true

for i = 1 to N-1 do
    if A[i] < A[i - 1] then
        set isAscending = false
    end if
    if A[i] > A[i - 1] then
        set isDescending = false
    end if
end for

if isAscending or isDescending then
    print "Yes, the array is sorted."
else
    print "No, the array is not sorted."
end if
</code></pre>

## Time Complexity:
O(N), where 'N' is the number of elements in the array. The solution involves a single traversal through the array.

## Space Complexity:
O(1), as no additional space dependent on the input size is used. Only a constant amount of space is used for the boolean flags.

## Sample Code in Java:

```java
import java.util.Scanner;

public class ArraySortedOrNot {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[] array = new int[N];

        // Read the array
        for (int i = 0; i < N; i++) {
            array[i] = scanner.nextInt();
        }

        boolean isAscending = true, isDescending = true;

        // Check if the array is sorted
        for (int i = 1; i < N; i++) {
            if (array[i] < array[i - 1]) {
                isAscending = false;
            }
            if (array[i] > array[i - 1]) {
                isDescending = false;
            }
        }

        // Output result
        if (isAscending || isDescending) {
            System.out.println("Yes, the array is sorted.");
        } else {
            System.out.println("No, the array is not sorted.");
        }
    }
}
