# Array Max-Min - Editorial

## Problem Analysis:
The "Array Max-Min" problem requires you to determine the maximum and minimum elements present in a given array 'A' of size 'N'. This problem tests your understanding of array traversal and basic comparison operations.

## Prerequisites:
- Arrays
- Looping (iteration)
- Basic knowledge of comparison operations

## Problem Statement:
Given an array 'A' consisting of 'N' elements, the task is to find and print the maximum and minimum elements of the array.

## Constraints:
- 1 <= N <= 1000
- 1 <= A[i] <= 10000

These constraints indicate that the problem's solution needs to work within reasonable time limits for an array of up to 1000 elements. Additionally, the values of the array elements are capped at 10000, which prevents issues related to integer overflow and underflow.

## Solution Approach:
The problem can be efficiently solved by iterating through the array once and maintaining the maximum and minimum values seen so far.

1. Initialize two variables, say 'maxValue' and 'minValue', with the first element of the array or the smallest and largest values of the integer range, respectively.
2. Traverse the array starting from the second element and compare each element with 'maxValue' and 'minValue'.
3. If the current element is greater than 'maxValue', update 'maxValue' with the current element.
4. If the current element is smaller than 'minValue', update 'minValue' with the current element.
5. Continue this process for each element in the array.
6. After the loop, 'maxValue' and 'minValue' hold the maximum and minimum values in the array, respectively.

## Pseudo Code:

<pre><code>
read N
read array A of size N
initialize maxValue as A[0]
initialize minValue as A[0]
for i = 1 to N - 1 do
    if A[i] > maxValue then
        maxValue = A[i]
    end if
    if A[i] < minValue then
        minValue = A[i]
    end if
end for
print maxValue, minValue
</code></pre>

## Time Complexity:
O(N), where 'N' is the number of elements in the array. This is because we're traversing the entire array once and performing constant-time operations at each step.

## Space Complexity:
O(1), as we are using only a constant amount of space (the variables 'maxValue' and 'minValue', and counter 'i') besides the input array itself.

## Sample Code in Java:

```java
import java.util.Scanner;

public class ArrayMaxMin {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Read the size of the array
        int N = scanner.nextInt();
        int[] A = new int[N];

        // Read the elements of the array
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        // Initialize maxValue and minValue with the first element of the array
        int maxValue = A[0];
        int minValue = A[0];

        // Find the maximum and minimum in the array
        for (int i = 1; i < N; i++) {
            if (A[i] > maxValue) {
                maxValue = A[i];
            }
            if (A[i] < minValue) {
                minValue = A[i];
            }
        }

        // Print the maximum and minimum values
        System.out.println("Max: " + maxValue + ", Min: " + minValue);
    }
}
