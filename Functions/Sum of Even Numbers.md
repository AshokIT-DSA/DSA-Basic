### **Sum of Even Numbers - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Arithmetic

### Problem Statement:
You're given a positive integer 'N'. Your task is straightforward: calculate the sum of all even numbers starting from 2 up to 'N' (inclusive). 

### Detailed Explanation:

1. **Understanding the Task:**
   This problem tests basic loop control and arithmetic operations. You need to iterate through a range of numbers, identify the even ones, and accumulate their sum. The challenge lies in constructing a loop that efficiently processes numbers within the given constraints.

2. **Solution Approach:**
   A simple solution involves iterating over each number in the range and checking if it is even. If it is, we add it to our running total. However, we can optimize by realizing that we don't need to check every number. Starting from 2, every second number is even. Therefore, we can start at 2 and skip ahead by 2s, directly adding each number we land on.

3. **Problem Constraints:**
   'N' is at most 2000. This constraint is relatively modest and should not cause any performance issues with the described approach. It's small enough to avoid any risk of overflow and doesn't necessitate advanced optimization techniques.

## Pseudo Code:

<pre><code>
read N
initialize sum as 0
for i = 2 to N in steps of 2 do:
    sum = sum + i  // Add the even number to our running total
end for
print sum
</code></pre>

### Time Complexity:
The time complexity is O(N/2), simplified to O(N), since we're essentially iterating through half of the elements from 1 to N.

### Space Complexity:
O(1), because we are using a fixed amount of space for our 'sum' variable regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class SumOfEvenNumbers {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt(); // Reading the input number
        int sum = 0; // Initialize the sum

        // Loop through the sequence, adding only the even numbers
        for (int i = 2; i <= N; i += 2) {
            sum += i; // Add the even number to the sum
        }

        System.out.println(sum); // Print the result
    }
}
