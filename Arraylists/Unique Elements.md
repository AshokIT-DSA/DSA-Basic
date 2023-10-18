### **Unique Elements - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Sorting, Looping, Basic Arithmetic, Greedy

### Problem Statement:
This problem involves writing a program that ensures all elements in an array 'A' of 'N' elements are unique. To achieve this, elements can be incremented by one step. The goal is to find the minimal number of steps required to make all elements distinct.

## Pseudo Code:

<pre><code>
read N
read array A

sort A

initialize steps to 0
for i from 1 to N-1 do
    if A[i] <= A[i - 1] then
        // Current element is not unique; increment it
        current_steps = A[i - 1] - A[i] + 1
        A[i] = A[i - 1] + 1
        steps = steps + current_steps
    end if
end for

print steps
</code></pre>

### Time Complexity:
O(N log N) due to the sorting of the array. The rest of the operations are linear, contributing an additional O(N) which is overshadowed by the sorting complexity.

### Space Complexity:
O(1), as the space taken by the input array is not counted towards space complexity and there is no significant extra space used, aside from a few variables for calculation.

## Sample Code (Java):

```java
import java.util.Arrays;
import java.util.Scanner;

public class UniqueElements {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[] A = new int[N];

        // Reading the array
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        // Sorting the array
        Arrays.sort(A);

        int steps = 0;

        // Making all elements unique
        for (int i = 1; i < N; i++) {
            if (A[i] <= A[i - 1]) {
                int current_steps = A[i - 1] - A[i] + 1;
                A[i] = A[i - 1] + 1;
                steps += current_steps;
            }
        }

        // Printing the number of steps
        System.out.println(steps);
    }
}
