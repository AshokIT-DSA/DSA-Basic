### **Odd Analysis - Editorial**
## Difficulty:- Easy

## Prerequisite:- Iteration, Condition Checking

### Problem statement:-
You are provided with a positive integer `N`. Your task is to print all odd numbers from 1 to `N`, each followed by a space.

### Short Explanation:-
Using a simple iterative approach, loop from 1 to `N`. For each number, check if it's odd. If it is, print the number followed by a space. With the given condition, it's fine to have a trailing space after the last odd number.

### Detailed Explanation:-

1. **Understanding the Problem:**  
   The problem is clear-cut. For a given positive integer `N`, you need to print odd numbers from 1 up to and including `N` in sequence.

2. **Iterating and Printing Odd Numbers:**  
   Start a loop from 1 and continue up to `N`. For each number in this range, check if the number is odd (i.e., `number % 2 != 0`). If the number is odd, print it followed by a space.

3. **Problem Constraints:**  
   As per the provided constraints:
   - \(1 \leq N \leq 10^5\)
   
   Our iterative approach will be effective and will run within a reasonable time frame for all inputs.

## Pseudo Code

<pre><code>
N = read input

for i = 1 to N:
    if i is odd:
        print i, followed by a space
</code></pre>

### Time Complexity:-
The overall time complexity is O(N) since we're iterating from 1 to `N` to check and print each odd number.

### Space Complexity:- 
O(1), as we're using a constant amount of space regardless of the size of the input.

## Sample Code (Java):

```java
import java.util.Scanner;

public class OddAnalysis {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int N = scanner.nextInt();

        for (int i = 1; i <= N; i++) {
            if (i % 2 != 0) {
                System.out.print(i + " ");
            }
        }
    }
}
```

By running the provided Java code, users can enter the positive integer `N`, and the program will then sequentially print the odd numbers from 1 to `N`, each separated by a space, including a trailing space after the last odd number.
