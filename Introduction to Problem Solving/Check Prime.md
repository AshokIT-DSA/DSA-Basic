### **Check Prime - Editorial**

## Difficulty: Easy

## Prerequisites: Loops, Basic Mathematics (Prime Numbers)

### Problem Statement:
You are tasked with determining whether a given number 'N' is prime. A prime number is a whole number greater than 1, whose only two whole-number factors are 1 and itself. The function should return true if the number is prime; otherwise, it should return false. Given the constraint that 'N' may be as large as 10<sup>9</sup>, the solution needs to be efficient in terms of both time and space.

### Detailed Explanation:

1. **Understanding the Task:**
   The challenge involves checking the primality of a number 'N'. This task is a classic problem that involves understanding prime numbers and efficiently determining whether a number is prime.

2. **Solution Approach:**
   A common approach to check if a number is prime is to try dividing it by all numbers less than it. However, this is not efficient, especially for large numbers. We only need to check divisibility up to the square root of 'N'. If 'N' is not divisible by any number up to its square root, it is prime.

   The algorithm proceeds as follows:
   - If 'N' is less than 2, it is not prime.
   - For all numbers 'i' from 2 to the square root of 'N':
     - If 'N' is divisible by 'i', it is not prime.
   - If no such 'i' is found, 'N' is prime.

3. **Problem Constraints:**
   The maximum possible value of 'N' is 10<sup>9</sup>. Due to this constraint, the algorithm must be optimized for performance to avoid a time-out error for large input values.

## Pseudo Code:

<pre><code>
read N
if N < 2 then return false
for i = 2 to sqrt(N) do:
    if N % i == 0 then:
        return false  // N is divisible by a number other than 1 and itself
    end if
end for
return true  // No divisor found; N is prime
</code></pre>

### Time Complexity:
The time complexity for this solution is O(sqrt(N)) because the loop checks divisibility only up to the square root of 'N', significantly reducing the number of iterations required, especially for large 'N'.

### Space Complexity:
O(1), as we are using only a constant amount of space. Our algorithm checks each divisor one by one and does not require storing a range of numbers or any complex data structures that depend on the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class CheckPrime {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Since the value can exceed the range of int, we use long
        System.out.println("Enter the number: ");
        long N = scanner.nextLong();
        
        // Method call to check if the number is prime
        boolean isPrime = isPrimeNumber(N);
        
        // Output the result
        System.out.println("Is prime: " + isPrime);
    }

    // Function to check if a number is prime
    public static boolean isPrimeNumber(long N) {
        if (N < 2) {
            return false; // Numbers less than 2 are not prime numbers
        }
        for (long i = 2; i <= Math.sqrt(N); i++) {
            if (N % i == 0) {
                return false; // Found a divisor, not a prime number
            }
        }
        return true; // No divisors found, it's a prime number
    }
}
```

### Conclusion:
This problem helps in understanding an optimized approach to check for a prime number, which is a fundamental concept in number theory and cryptography. The optimization part, where we reduce the number of required iterations to only up to the square root of 'N', is particularly useful in cases dealing with large numbers, ensuring our solution is efficient and scalable.