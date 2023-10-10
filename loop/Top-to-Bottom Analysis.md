# **Top-to-Bottom Analysis**
## Difficulty:- Easy

## Prerequisite:- Iteration

### Problem statement:-
You are provided with a positive integer `N`. Your task is to print natural numbers from 1 to `N`, each followed by a space, but not after the last number.

### Short Explanation:-
Using a simple iterative approach, you can loop from 1 to `N` and print each number, followed by a space, ensuring that the last number does not have a trailing space.

### Detailed Explanation:-

1. **Understanding the Problem:**  
   The problem is straightforward. Given a positive integer `N`, you need to print numbers from 1 up to and including `N` in a sequence.

2. **Iterating and Printing:**  
   Start a loop from 1 and continue up to `N`. Print each number followed by a space. However, make sure that after printing the last number (`N`), you don't print a space.

3. **Problem Constraints:**  
   Given constraints are:
   - \(1 \leq N \leq 10^6\)
   
   Given the constraints, our iterative approach will be efficient and will finish in a reasonable time for all inputs.

## Pseudo Code

<pre><code>
N = read input

for i = 1 to N:
    print i,
    if i is not N:
        print space
</code></pre>

### Time Complexity:-
The overall complexity is O(N) as we're iterating from 1 to `N` to print each number.

### Space Complexity:- 
O(1), as we are using a constant amount of space regardless of the input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class PrintNaturalNumbers {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            System.out.print(i);
            if (i != N) {
                System.out.print(" ");
            }
        }
    }
}
```

By running the above Java code, users can input the positive integer `N`, and the program will then sequentially print the numbers from 1 to `N`, each separated by a space, without a trailing space after the last number.
## Note :- Writing if condition is optional you can also display the result in this way as well. 
###  System.out.print(i+" ");
