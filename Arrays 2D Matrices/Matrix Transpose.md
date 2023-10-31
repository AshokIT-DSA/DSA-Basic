### **Matrix Transpose - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- 2D Arrays
- Matrix operations

---

### **Problem:**
The transpose of a matrix is a new matrix whose rows are the columns of the original. This is achieved by flipping the matrix over its main diagonal. The main diagonal of a matrix is the diagonal stretch from its top left to its bottom right. 

---

### **Approach:**
The solution is straightforward as the problem simply requires the rows to be swapped with the columns. For an element at position `(i, j)` in the original matrix, its position in the transposed matrix will be `(j, i)`.

1. **Initialization:**
   - Read the dimensions of the matrix: `N` (rows) and `M` (columns).
   - Create a 2D array or matrix of size `N x M` and populate it with the given elements.

2. **Transpose:**
   - Iterate through each column (outer loop for `i` from `0` to `M-1`).
   - For each column, iterate through each row (inner loop for `j` from `0` to `N-1`) and print the element at `(j, i)`.
   - After each column (i.e., at the end of the inner loop), print a newline to start the next row of the transposed matrix.

3. **Output:**
   - The transposed matrix is printed row by row.

### **Algorithm:**
```plaintext
Begin
    Read the dimensions of the matrix: N and M
    Initialize a 2D array 'matrix' of size 'N x M' and read input elements
    For i from 0 to M-1 (represents column of original matrix)
        For j from 0 to N-1 (represents row of original matrix)
            Print matrix[j][i] followed by a space
        EndFor
        Print a newline to move to the next row of the transposed matrix
    EndFor
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N*M)
  - We are simply iterating through every element of the original matrix once. So, the time complexity is O(N*M) where N is the number of rows and M is the number of columns of the matrix.

- **Space Complexity:** O(N*M)
  - This is mainly because of the space taken up by the original matrix. No additional space (ignoring the space for variables) is required for this algorithm.

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt(); // Number of rows
        int M = sc.nextInt(); // Number of columns
        int[][] matrix = new int[N][M];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }

        // Printing the transpose of the matrix
        for (int i = 0; i < M; i++) {
            for (int j = 0; j < N; j++) {
                System.out.print(matrix[j][i] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### **Conclusion:**
This problem is a simple demonstration of matrix operations and handling 2D arrays. It's a basic exercise in understanding how to transpose a matrix and should be a good starting point for those unfamiliar with 2D arrays or matrix operations.