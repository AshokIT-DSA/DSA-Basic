### **Print Ath Month - Editorial**
## Difficulty:- Easy

## Prerequisite:- Arrays, Basic Input/Output 

### Problem statement:-
Given an integer A, where 1 ≤ A ≤ 12, determine and print the name of the Ath month of the year. 
 
### Short Explanation:-
This problem can be solved easily using an array. 
1. Store all the months of the year in an array.
2. Access the (A-1)th index of the array to get the Ath month.

### Detailed Explanation:-

1. **Creating an Array of Months**   
   Firstly, create an array that holds all the months in order. 

2. **Fetching the Ath month**  
   If the user provides an integer A, then the name of the Ath month is stored at index `A-1` of the months array. This is because array indexing starts from 0. So, January is at index 0, February is at index 1, and so on.

3. **Edge Case**  
   Ensure that the provided integer A is between 1 and 12. If not, inform the user that the input is invalid.

## Pseudo Code

<pre><code>
function printMonth(A) {
    months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];

    if (A >= 1 && A <= 12) {
        print(months[A-1]);
    } else {
        print("Invalid Input");
    }
}
</code></pre>

### Time Complexity:-
The overall complexity of the `printMonth` function is O(1), as accessing an element from an array using its index takes constant time.

### Space Complexity:- 
O(1), as the space required for the months array is constant irrespective of the input.

## Java Code:

```java
import java.util.Scanner;

public class MonthName {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the month number (A): ");
        int A = scanner.nextInt();
        
        String[] months = {"January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"};

        if(A >= 1 && A <= 12) {
            System.out.println(months[A-1]);
        } 
    }
}
```

The user can run the above code, provide the month number when prompted, and get the name of the respective month.