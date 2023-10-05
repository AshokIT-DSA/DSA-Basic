### **Electricity Bill Calculation - Editorial**
## Difficulty:- Easy

## Prerequisite:- Arithmetic Operations, If-Else 

### Problem statement:-
Mr. T received an electricity bill and is curious to understand the relationship between the amount and the number of units. You are provided with the tariff details. Your task is to:
1. Calculate the bill amount based on the given tariff structure.
2. Determine the integral value of the calculated amount.

### Short Explanation:-
1. Calculate the amount for the units consumed using the given rate structure.
2. Add a 20% surcharge to the calculated amount.
3. Return the integral value of the total amount.

### Detailed Explanation:-

1. **Bill Calculation for 0-50 Units:**  
   For the first 50 units, the rate is Rs. 0.50/unit.

2. **Bill Calculation for 51-150 Units:**  
   For the next 100 units (i.e., 51 to 150), the rate is Rs. 0.75/unit.

3. **Bill Calculation for 151-250 Units:**  
   For the next 100 units (i.e., 151 to 250), the rate is Rs. 1.20/unit.

4. **Bill Calculation for Units above 250:**  
   For units above 250, the rate is Rs. 1.50/unit.

5. **Adding Surcharge:**  
   After calculating the initial bill based on the above rates, add a surcharge of 20%.

6. **Final Bill Amount:**  
   Return the integral value of the total bill amount.

## Pseudo Code

<pre><code>
function calculateBill(N) {
    if (N <= 50) {
        amount = N * 0.50;
    } else if (N <= 150) {
        amount = (50 * 0.50) + (N - 50) * 0.75;
    } else if (N <= 250) {
        amount = (50 * 0.50) + (100 * 0.75) + (N - 150) * 1.20;
    } else {
        amount = (50 * 0.50) + (100 * 0.75) + (100 * 1.20) + (N - 250) * 1.50;
    }

    totalBill = amount + (0.20 * amount);
    
    print(Integral Value of totalBill);
}
</code></pre>

### Time Complexity:-
The overall complexity of the `calculateBill` function is O(1), as all operations are performed in constant time.

### Space Complexity:- 
O(1), as no extra space is used regardless of the input.

## Java Code:

```java
import java.util.Scanner;

public class ElectricityBill {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the number of units consumed (N): ");
        int N = scanner.nextInt();

        double amount;

        if (N <= 50) {
            amount = N * 0.50;
        } else if (N <= 150) {
            amount = (50 * 0.50) + (N - 50) * 0.75;
        } else if (N <= 250) {
            amount = (50 * 0.50) + (100 * 0.75) + (N - 150) * 1.20;
        } else {
            amount = (50 * 0.50) + (100 * 0.75) + (100 * 1.20) + (N - 250) * 1.50;
        }

        double totalBill = amount + (0.20 * amount);

        System.out.println("Bill Amount: " + (int)totalBill);
    }
}
```

Users can run the above code, input the number of units consumed, and see their bill's integral value.