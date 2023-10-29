### **Sum of Minor Diagonal Elements - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays (2D)
- Diagonals in a matrix
- Basic iteration (looping)

---

### **Problem:**
The task is to calculate the sum of elements located on the minor diagonal of a given square matrix. The minor diagonal is the diagonal stretching from the top-right to the bottom-left of the matrix.

---

### **Approach:**
The minor diagonal elements of a square matrix are those for which the sum of the row index and column index equals N - 1 (using 0-based indexing) or simply the column index is `N - 1 - row index`. 

1. **Initialization:**
   - Read the dimension 'N' of the square matrix.
   - Create a 2D array or matrix of size 'N x N' and populate it with the given elements.

2. **Finding the Sum of Minor Diagonal Elements:**
   - Initialize a variable to hold the sum of the diagonal elements.
   - Loop through the matrix, and at each row, calculate the column index of the minor diagonal element as `N - 1 - row index`. Add the element at the current position to the sum. Here, the current position in each step of the loop is given by (i, N - 1 - i) where 'i' is the row index or loop variable.

3. **Output:**
   - After the loop ends, print the calculated sum.

### **Algorithm:**
```plaintext
Begin
    Read the dimension N of the matrix
    Initialize a 2D array 'matrix' of size 'N x N' with input elements
    Initialize 'sum' to 0
    For 'i' from 0 to N-1
        Calculate 'j' as 'N - 1 - i'
        Add 'matrix[i][j]' to 'sum'
    EndFor
    Print 'sum'
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N)
  - We are running a single loop through the matrix, and the number of iterations is equal to the dimension of the matrix, which gives us a time complexity of O(N).

- **Space Complexity:** O(N^2)
  - We are using a 2D array to store the matrix elements. This array takes up N * N space. The rest of the variables use constant space.

---

## **Java Solution:**
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Read the dimension of the matrix
        int N = scanner.nextInt();

        // Initialize the matrix and read its contents
        int[][] matrix = new int[N][N];
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        // Compute the sum of the minor diagonal
        int diagonalSum = 0;
        for (int i = 0; i < N; i++) {
            diagonalSum += matrix[i][N - 1 - i];
        }

        // Print the result
        System.out.println(diagonalSum);
    }
}
```

---

### **Conclusion:**
This problem is an excellent continuation from understanding the main diagonal in a matrix to the minor diagonal. It helps solidify the understanding of matrix traversal and manipulation, building up knowledge incrementally for more complex operations on matrices or two-dimensional arrays.