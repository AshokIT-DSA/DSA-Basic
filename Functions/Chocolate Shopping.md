### **Chocolate Shopping - Editorial**

## Difficulty: Easy

## Prerequisites: Arithmetic, Math, Basic Programming

### Problem Statement:
Rahul enjoys chocolates but is both budget-conscious and health-conscious. He has 'A' rupees and wants to maximize the number of chocolates he purchases without exceeding his health limit of 'C' chocolates or his budget. Each chocolate costs 'B' rupees. The task is to determine the number of chocolates Rahul will buy.

### Detailed Explanation:

1. **Understanding the Task:**
   The task requires a simple mathematical calculation. You are given three variables:
   - 'A': the total amount of money Rahul has.
   - 'B': the cost of one chocolate.
   - 'C': the maximum number of chocolates Rahul is willing to purchase for health reasons.

   The objective is to find out the maximum number of chocolates Rahul can buy without exceeding his budget and health constraint.

2. **Solution Approach:**
   Firstly, we need to calculate the maximum number of chocolates that Rahul's budget allows. This is done by dividing his total money 'A' by the cost of one chocolate 'B'. However, this number might exceed Rahul's health constraint 'C'. 

   So, we compare this number with 'C' and choose the smaller value. This ensures Rahul buys the maximum number of chocolates possible without violating his constraints.

3. **Problem Constraints:**
   Since all values are guaranteed to be less than or equal to 10^6, the computations will comfortably fall within the range of 'int' or 'long' data types, preventing overflow.

## Pseudo Code:

<pre><code>
read A, B, C
// Calculate the maximum number of chocolates that can be bought with the available money
maxChocolatesByBudget = A / B
// Rahul will buy the lesser of the two: the number of chocolates his budget allows, or his health constraint
chocolatesRahulWillBuy = min(maxChocolatesByBudget, C)
print chocolatesRahulWillBuy
</code></pre>

### Time Complexity:
The time complexity is O(1), as the problem involves basic arithmetic calculations that don't depend on the input size.

### Space Complexity:
O(1), because the solution uses a constant amount of space, regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class ChocolateShopping {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int A = scanner.nextInt(); // Money Rahul has
        int B = scanner.nextInt(); // Cost of one chocolate
        int C = scanner.nextInt(); // Maximum number of chocolates Rahul intends to buy

        // Calculating maximum chocolates Rahul can buy with his budget
        int maxChocolatesByBudget = A / B;

        // Calculating the actual number of chocolates Rahul will buy considering his health
        int chocolatesRahulWillBuy = Math.min(maxChocolatesByBudget, C);

        // Output the result
        System.out.println(chocolatesRahulWillBuy);
    }
}
