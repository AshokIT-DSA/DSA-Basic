### **Check Number's Nature - Editorial**
## Difficulty:- Easy

## Prerequisite:- Basic Understanding of If-Else 

### Problem statement:-
Given an integer, determine if it's positive, negative, or neither and print:
- `1` if it is positive.
- `-1` if it is negative.
- `0` if it's neither positive nor negative.

### Short Explanation:-
This problem requires a basic understanding of conditions. 
1. Check if the number is greater than 0, if yes then it's positive.
2. Else check if it's less than 0, then it's negative.
3. Else it's 0.

### Detailed Explanation:-

**Case 1: Positive Number**  
If the number A is greater than 0, then it is a positive number.

**Case 2: Negative Number**  
If the number A is less than 0, then it is a negative number.

**Case 3: Neither Positive Nor Negative**  
If the number A is not greater than 0 and not less than 0, then it must be 0.

Using the above three cases, you can determine the nature of the number and print the respective output.

## Pseudo Code

<pre><code>
function checkNumberNature(A) {
    if(A > 0) {
        print(1);
    } else if(A < 0) {
        print(-1);
    } else {
        print(0);
    }
}
</code></pre>

### Time Complexity:-
The overall complexity of the `checkNumberNature` function is O(1), as it involves only constant time comparisons.

### Space Complexity:- 
O(1), as no extra space is used.

## Java Code:

```java
import java.util.Scanner;

public class NumberNature {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the number A: ");
        int A = scanner.nextInt();
        
        if(A > 0) {
            System.out.println(1);
        } else if(A < 0) {
            System.out.println(-1);
        } else {
            System.out.println(0);
        }
    }
}
```

The user can now run the above code, input the number when prompted, and get the desired output.