### **Reverse Array Elements in a Range - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Two-pointer Technique

### Problem Statement:
You are tasked with reversing a segment of an array of integers. Given the array and two indices, X and Y, you need to reverse the order of elements lying between (and including) positions X and Y.

### Detailed Explanation:

1. **Understanding the Task:**
   We're dealing with a classic array manipulation problem where the task is to reverse a subsequence within the array without affecting other elements. This operation must be done in place to keep the space complexity at a minimum.

2. **Solution Approach:**
   The optimal solution here uses the two-pointer technique. The idea is to set one pointer at the start index (X) and the other at the end index (Y) of the sequence to be reversed. Then, we swap the elements at these two pointers and move the pointers toward each other (X gets incremented, and Y gets decremented) until they meet or cross paths.

   This approach doesn't require any additional space proportional to the array size and maintains the integrity of the rest of the array.

3. **Problem Constraints:**
   With the constraints provided (1 <= N <= 10^5, 1 <= A[i] <= 10^8, and 1 <= X <= Y <= N - 1), this method will efficiently perform the required operation within the limits.

## Pseudo Code:

```plaintext
read N, X, Y, A[N]

// Set pointers at the specified indices
leftPointer = X
rightPointer = Y

// Continue swapping until pointers meet
while leftPointer < rightPointer do:
    swap A[leftPointer] with A[rightPointer]
    leftPointer++
    rightPointer--
end while

print A[N]
```

### Time Complexity:
The time complexity for this approach is O(N), even though we are only iterating through a portion of the array (from X to Y). This is because, in the worst-case scenario, the range could cover the entire array.

### Space Complexity:
The space complexity is O(1) since no extra space dependent on input size is used. Only a couple of additional variables are needed for the pointers and the temporary storage during the swap.

## Sample Code (Java):

```java
import java.util.Scanner;

public class ReverseInRange {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Read inputs
        int N = scanner.nextInt();
        int X = scanner.nextInt();
        int Y = scanner.nextInt();
        int[] array = new int[N];
        for (int i = 0; i < N; i++) {
            array[i] = scanner.nextInt();
        }

        // Close scanner
        scanner.close();

        // Reverse the segment [X, Y] in the array
        while (X < Y) {
            int temp = array[X];
            array[X] = array[Y];
            array[Y] = temp;
            X++;
            Y--;
        }

        // Output the modified array
        for (int i : array) {
            System.out.print(i + " ");
        }
    }
}
```

### Conclusion:
This problem tests array manipulation skills and understanding of in-place operations. The two-pointer technique is a powerful tool in scenarios where manipulating sequences within arrays or other data structures is required, allowing for optimal time and space complexity.