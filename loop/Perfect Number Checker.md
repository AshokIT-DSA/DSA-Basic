### **Perfect Number Checker - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Condition Checking, Summation

### Problem Statement:
You are tasked with identifying whether a number 'N' is a perfect number or not, given 'T' test cases. A perfect number is a positive integer that is equal to the sum of its proper positive divisors, excluding itself. The program should efficiently handle the constraints and return the correct result for each test case.

### Detailed Explanation:

1. **Understanding Perfect Numbers:**
   A perfect number is uniquely identified by its characteristics of being equal to the sum of its divisors (excluding itself). For instance, 6 is a perfect number because its divisors are 1, 2, and 3, and 1 + 2 + 3 = 6.

2. **Efficient Calculation of Divisors:**
   Instead of iterating through all the numbers below 'N', iterate only up to the square root of 'N'. Each time you find a number that divides 'N', add both the divisor and the quotient to the sum, but be careful not to add the square root twice if 'N' is a perfect square.

3. **Checking for Perfection:**
   After obtaining the sum of divisors, compare it with 'N'. If they're equal, 'N' is a perfect number. Otherwise, it's not.

4. **Problem Constraints:**
   With 'N' ranging up to \(10^6\) and up to 10 test cases, the algorithm needs to be efficient to run within the time limits.

## Pseudo Code:

<pre><code>
read T
while T > 0:
    read N
    sum = 1  // 1 is a proper divisor
    for i = 2 to sqrt(N) do:
        if N % i == 0:
            sum += i
            if i != N/i:
                sum += N/i
    end for
    if sum == N and N != 1:
        print "Perfect number"
    else:
        print "Not a perfect number"
    T--
end while
</code></pre>

### Time Complexity:
The time complexity is O(sqrt(N)) per test case, as we only iterate up to the square root of 'N' to find its divisors.

### Space Complexity:
O(1), since we're using a constant amount of space.

## Sample Code (Java):

```java
import java.util.Scanner;

public class PerfectNumberChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = scanner.nextInt();

        while (T-- > 0) {
            int N = scanner.nextInt();
            int sum = 1;  // 1 is always a proper divisor

            for (int i = 2; i <= Math.sqrt(N); i++) {
                if (N % i == 0) {
                    sum += i;
                    if (i != N / i) {
                        sum += N / i;  // add the quotient if it's different
                    }
                }
            }

            if (sum == N && N != 1) {
                System.out.println("Perfect number");
            } else {
                System.out.println("Not a perfect number");
            }
        }
    }
}
