### **Fruit Shake Glasses - Editorial**

## Difficulty: Easy

## Prerequisites: Arithmetic, Math, Basic Programming

### Problem Statement:
You have a certain number of fruits 'A' and slices 'B', with each fruit capable of being sliced into three more pieces. Each glass of fruit shake needs two slices. The problem requires you to figure out the maximum number of glasses you can prepare with your resources.

### Detailed Explanation:

1. **Understanding the Task:**
   This is essentially a problem of simple arithmetic and resource optimization. You need to maximize the number of fruit shake glasses, which depends on the availability of slices. You start with 'B' slices, and every fruit you slice adds three more slices to your inventory.

2. **Solution Approach:**
   To solve this, you first need to calculate the total number of slices. You already have 'B' slices, and slicing 'A' fruits would give you 3 * 'A' more slices. Once you have the total slices, you need to see how many glasses you can prepare. Since each glass requires two slices, you divide the total number of slices by two to get the number of glasses.

   However, the division could result in a fractional number if the total slices are odd, but you can't make a half glass of shake, so you take the integer part of the division (effectively rounding down any fraction).

3. **Problem Constraints:**
   With the maximum value of 'A' and 'B' being 10^8, you need to use a data type capable of handling values potentially going up to 3 * 10^8 without overflow (for instance, 'int' in languages like Java or Python).

## Pseudo Code:

<pre><code>
read A, B
// Calculate the total number of slices after cutting all fruits
totalSlices = (A * 3) + B
// Calculate the number of glasses by dividing by 2, considering only full glasses can be made
numberOfGlasses = totalSlices // 2  (This is integer division, discarding the fractional part)
print numberOfGlasses
</code></pre>

### Time Complexity:
The time complexity is O(1), as the problem involves only direct arithmetic operations, which do not depend on input size.

### Space Complexity:
O(1), because the solution uses a constant amount of space, regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class FruitShakeGlasses {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt(); // Number of fruits
        int B = scanner.nextInt(); // Initial number of slices

        // Total slices after slicing all fruits
        int totalSlices = (A * 3) + B;

        // Calculating the number of full glasses of shake
        int numberOfGlasses = totalSlices / 2; // integer division

        // Output the result
        System.out.println(numberOfGlasses);
    }
}
