### **Check_Prime - Editorial**

## Difficulty: Easy

## Prerequisites: Basic Mathematics, Primality Test, Loops

### Problem Statement:
Given a number `N`, determine whether it is a prime number. If `N` is prime, return true; otherwise, return false. A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself. It's essential to handle large numbers efficiently as `N` can be as large as 10<sup>8</sup>.

### Detailed Explanation:

1. **Understanding Primality:**
   To check if a number is prime, we need to see if it has any divisors other than 1 and itself. However, brute force checking all numbers less than `N` is inefficient, especially for large `N`.

2. **Optimizing Divisor Checks:**
   We can optimize by checking only up to the square root of `N`. If `N` is divisible by any number up to its square root, it's not prime. This approach significantly reduces the number of necessary checks.

3. **Special Cases:**
   Handle small cases separately. For example, numbers less than 2 are not prime, and 2 is a prime number. These cases can be hardcoded for efficiency.

4. **Problem Constraints:**
   With 'N' ranging up to \(10^8\), our solution needs to be optimized to run within a reasonable time frame for all possible inputs.

## Pseudo Code:

<pre><code>
function isPrime(N) {
    if N <= 1 return false
    if N == 2 return true
    if N % 2 == 0 return false  // eliminate even numbers > 2
    for i = 3 to sqrt(N) step 2 do:
        if N % i == 0 return false
    end for
    return true
}
</code></pre>

### Time Complexity:
The time complexity for the prime check is approximately O(sqrt(N)) because the loop runs from 3 to sqrt(N), and we only check the odd divisors.

### Space Complexity:
O(1), as we're not using significant extra storage relative to the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class Check_Prime {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the number N: ");
        long N = scanner.nextLong();  // using long for larger numbers
        
        System.out.println(isPrime(N));
    }
    
    public static boolean isPrime(long N) {
        if (N <= 1) return false;  // numbers less than 2 are not prime
        if (N == 2) return true;  // 2 is a prime number
        if (N % 2 == 0) return false;  // eliminate even numbers > 2
        for (long i = 3; i <= Math.sqrt(N); i += 2) {
            if (N % i == 0) return false;  // check divisibility
        }
        return true;
    }
}
