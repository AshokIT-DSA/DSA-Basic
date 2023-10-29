### **Sum of Main Diagonal - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays (2D)
- Diagonals in a matrix
- Basic iteration (looping)

---

### **Problem:**
The problem is straightforward and requires us to find and sum the elements of the main diagonal in a square matrix. The main diagonal of a matrix is the one stretching from the top-left to the bottom-right corner.

---

### **Approach:**
The main diagonal elements of a square matrix are those elements that have the same row and column index. Therefore, for a matrix of size N x N, the main diagonal elements are those at positions (0,0), (1,1), ..., (N-1,N-1).

1. **Initialization:**
   - Read the dimension 'N' of the square matrix.
   - Create a 2D array or matrix of size 'N x N' and initialize it with the given elements.

2. **Finding the Sum of Diagonal Elements:**
   - Initialize a variable to hold the sum of the diagonal elements.
   - Loop through the matrix from (0,0) to (N-1,N-1), and at each step, add the element at the current position to the sum.
   - The current position in each step of the loop is given by (i,i) where 'i' is the loop variable.

3. **Output:**
   - After the loop ends, print the calculated sum.

### **Algorithm:**
```plaintext
Begin
    Read the dimension N of the matrix
    Initialize a 2D array 'matrix' of size 'N x N' with the input elements
    Initialize 'sum' to 0
    For 'i' from 0 to N-1
        Add 'matrix[i][i]' to 'sum'
    EndFor
    Print 'sum'
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N)
  - We are running a single loop through the matrix, and the number of iterations is equal to the dimension of the matrix, which gives us a time complexity of O(N).

- **Space Complexity:** O(N^2)
  - We are using a 2D array to store the matrix elements. This array takes up N * N space. The rest of the variables use constant space.

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

        // Compute the sum of the main diagonal
        int diagonalSum = 0;
        for (int i = 0; i < N; i++) {
            diagonalSum += matrix[i][i];
        }

        // Print the result
        System.out.println(diagonalSum);
    }
}
```

---

### **Conclusion:**
This problem is an excellent practice for understanding indexing in two-dimensional arrays and the concept of the main diagonal in a matrix. It combines array manipulation with a straightforward mathematical operation, making it a good introductory problem for learning about data structures and algorithms.