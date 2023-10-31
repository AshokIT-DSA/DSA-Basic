### **Matrix Rotation - Editorial**

---

## **Difficulty: Easy-Medium**

---

## **Prerequisites:**
- 2D Arrays
- Matrix operations

---

### **Problem:**
The task is to rotate a given square matrix by 90 degrees in a clockwise direction. The problem can be solved using various methods, but the main challenge is to do this transformation in-place without using any additional array.

---

### **Approach:**
There's a very elegant approach to do this in-place. The steps are:

1. **Transpose the Matrix:** 
    - A matrix transpose is achieved by swapping `matrix[i][j]` with `matrix[j][i]` for each `i` and `j`. 
    - After transposition, the matrix will be a mirror image of the original matrix about the main diagonal (from top-left to bottom-right).
    
2. **Reverse the Columns:**
    - After transposition, to get the 90-degree clockwise rotation, reverse the order of columns. This means that the first column becomes the last column, the second becomes the second last, and so on.

### **Algorithm:**
```plaintext
Begin
    Read the dimension of the matrix: N
    Initialize a 2D array 'matrix' of size 'N x N' and read input elements

    // Transpose the matrix
    For i from 0 to N-1
        For j from i+1 to N-1 
            Swap matrix[i][j] with matrix[j][i]
        EndFor
    EndFor

    // Reverse columns of the matrix
    For i from 0 to N-1
        For j from 0 to N/2 - 1
            Swap matrix[i][j] with matrix[i][N-j-1]
        EndFor
    EndFor

    // Print the rotated matrix
    For i from 0 to N-1
        For j from 0 to N-1
            Print matrix[i][j] followed by a space
        EndFor
        Print a newline
    EndFor
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N^2)
  - Since we are iterating through each element of the matrix twice (once for transpose and once for reversing columns), the time complexity is O(N^2).

- **Space Complexity:** O(1)
  - The rotation is done in-place, so no additional memory is used apart from the input matrix and a few variables. The space complexity is therefore O(1).

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt(); // Dimension of matrix
        int[][] matrix = new int[N][N];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }

        // Transpose the matrix
        for (int i = 0; i < N; i++) {
            for (int j = i + 1; j < N; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            }
        }

        // Reverse columns of the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N / 2; j++) {
                int temp = matrix[i][j];
                matrix[i][j] = matrix[i][N - j - 1];
                matrix[i][N - j - 1] = temp;
            }
        }

        // Printing the rotated matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### **Conclusion:**
This problem is a good exercise in handling 2D arrays and manipulating matrices. The in-place approach ensures efficient utilization of memory, making the solution optimal for large matrices.