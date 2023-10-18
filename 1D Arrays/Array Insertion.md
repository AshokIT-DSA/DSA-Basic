### **Array Insertion - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Looping, Data Manipulation

### Problem Statement:
This task requires you to work with arrays directly. You're given an array of 'n' elements. Additionally, you're provided with two integers 'X' and 'Y'. You need to insert 'Y' into the given array at the position 'X', then output the resulting array. Remember, 'X' uses 1-based indexing, meaning the first position in the array is considered position 1. Upon insertion, elements at or beyond 'X' shift one position to the right.

### Detailed Explanation:

1. **Understanding the Task:**
   The problem is about array manipulation, specifically, inserting an element into an array at a specified position. It checks your understanding of array data structure, indexing, and element shifting following an insertion.

2. **Solution Approach:**
   One approach is to create a new array of size 'n+1' to accommodate the new element. You would copy all elements from the old array to the new one up to position 'X-1', place 'Y' at position 'X', and then continue copying the rest. However, an in-place solution could also shift elements from the end of the array to the right, starting from the last element until reaching position 'X', making room to insert 'Y'.

3. **Problem Constraints:**
   With 'N' maxing at 1000, we avoid large-scale data performance issues. The element insertion and shifting operation can be done efficiently within these constraints.

## Pseudo Code:

<pre><code>
read N
read array of size N
read X, Y
// Shift elements to the right from the end to position X
for i = N down to X do:
    array[i] = array[i - 1]
end for
// Insert the new element
array[X - 1] = Y  // Adjusting for 0-based indexing in the array
print array
</code></pre>

### Time Complexity:
The time complexity is O(N) because, in the worst case, we might need to shift all elements of the array by one position.

### Space Complexity:
O(1), if we manipulate the array in place without initializing a new array. Otherwise, O(N) for the space of the new array.

## Sample Code (Java):

```java
import java.util.Scanner;

public class ArrayInsertion {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt(); // Size of the array
        int[] array = new int[N+1]; // Declare an array with one extra space for the new element

        // Read the array
        for (int i = 0; i < N; i++) {
            array[i] = scanner.nextInt();
        }

        int X = scanner.nextInt(); // Position to insert
        int Y = scanner.nextInt(); // Element to insert

        // Shift elements from position X to the right
        for (int i = N; i >= X; i--) {
            array[i] = array[i - 1];
        }

        array[X - 1] = Y; // Insert the element at the correct position (adjusting for 0-based indexing)

        // Print the updated array
        for (int i = 0; i <= N; i++) {
            System.out.print(array[i] + " ");
        }
    }
}
