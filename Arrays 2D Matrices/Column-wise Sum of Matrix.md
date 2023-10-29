### **Column-wise Sum of Matrix - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Matrices (2D Arrays)
- Iteration (looping)

---

### **Problem Statement:**
This problem asks for the computation of the sum of elements for each column in a given matrix (2D array) and output each sum separated by a newline.

---

### **Solution Approach:**

A straightforward approach to solving this problem involves the use of nested loops to iterate over each column of the matrix while maintaining a running sum of elements.

1. **Initialization:**
   - Read the dimensions of the matrix (N x M).
   - Read the elements of the matrix.

2. **Column-wise Sum Calculation:**
   - Iterate from the first column to the last.
   - For each column, initialize a variable to keep the sum of the elements.
   - Further iterate through each row of the current column, adding the value at the cell to the running sum.
   - After completing the iteration for a particular column, output the calculated sum.

### **Algorithm Steps:**
```plaintext
Begin
    Read N, M (dimensions of the matrix)
    Initialize the 2D matrix with given elements
    For col from 0 to M-1
        Initialize sum as 0
        For row from 0 to N-1
            Add matrix[row][col] to sum
        EndFor
        Print sum followed by a newline
    EndFor
End
```

### **Time Complexity:**
The algorithm runs in O(N * M) time complexity since it involves a nested loop that goes through each element of the matrix exactly once. 

### **Space Complexity:**
The space complexity is O(N * M) for storing the matrix. No additional space is used, keeping the space requirement minimal.

## **Java Solution:**
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Read the dimensions of the matrix
        int N = scanner.nextInt();
        int M = scanner.nextInt();

        // Read the matrix
        int[][] matrix = new int[N][M];
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        // Calculate and print column-wise sum
        for (int j = 0; j < M; j++) {
            int sum = 0;
            for (int i = 0; i < N; i++) {
                sum += matrix[i][j];
            }
            System.out.println(sum);
        }
    }
}
```

---

### **Conclusion:**
The problem is solved by directly applying basic matrix manipulation techniques. It involves iterating over the matrix and understanding how to navigate through its elements, reinforcing the concepts of working with 2D arrays. This method is efficient and direct, given the constraints of the problem.