### **Anti-Diagonals - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays (2D)
- Diagonals in a matrix
- Basic iteration (looping)

---

### **Problem:**
The task is to generate an array of anti-diagonals of a given square matrix. Here, anti-diagonals are the diagonals stretching from each element in the first row and the last column to the elements in the first column or last row. Each row in the resulting array represents an anti-diagonal of the matrix, and if the anti-diagonal doesn't fill the entire row, the remaining spaces should be filled with zeros.

---

### **Approach:**
The solution involves iterating through each element that starts an anti-diagonal (elements of the first row and the last column), then traversing the matrix to collect the anti-diagonal elements. After collecting the elements, we need to add zeros to make each part of the output consistent in length with the matrix dimension.

1. **Initialization:**
   - Read the dimension 'N' of the square matrix.
   - Create a 2D array or matrix of size 'N x N' and populate it with the given elements.

2. **Collecting Anti-diagonal Elements:**
   - Initialize a list of lists to hold the anti-diagonal elements.
   - There will be '2*N - 1' anti-diagonals in an 'N x N' matrix. This count includes the main diagonal, the diagonals above, and the diagonals below the main diagonal.
   - Iterate through this number of anti-diagonals. For each diagonal, use appropriate starting points and collect the elements that lie on the current anti-diagonal. After each diagonal is processed, check the number of elements. If it is less than 'N', fill the remaining positions with zeros.

3. **Output:**
   - After preparing the list of anti-diagonals, print each list as a separate line, ensuring the elements are space-separated.

### **Algorithm:**
```plaintext
Begin
    Read the dimension N of the matrix
    Initialize a 2D array 'matrix' of size 'N x N' with input elements
    Initialize a list of lists 'antiDiagonals'
    For 'd' from 0 to (2*N - 1)
        Initialize a list 'currentDiagonal'
        If 'd' is less than 'N'
            Collect elements from top-right to bottom-left, starting at column 'd'
        Else
            Collect elements starting one row below the top row, moving from right to left
        EndIf
        While the size of 'currentDiagonal' is less than 'N'
            Add 0 to 'currentDiagonal'
        EndWhile
        Add 'currentDiagonal' to 'antiDiagonals'
    EndFor
    Print 'antiDiagonals' each list on a new line
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N^2)
  - We are running loops that collectively iterate through each element of the matrix exactly once. This gives us a time complexity directly proportional to the number of elements, which is N^2 for an N x N matrix.

- **Space Complexity:** O(N^2)
  - The output list of lists and the input matrix both take space proportional to the square of the dimensions of the matrix. The additional space for the temporary lists and variables is negligible compared to this.

---

## **Java Solution:**
```java
import java.util.ArrayList;
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();

        // Reading input matrix
        for (int i = 0; i < N; i++) {
            ArrayList<Integer> row = new ArrayList<>();
            for (int j = 0; j < N; j++) {
                row.add(sc.nextInt());
            }
            matrix.add(row);
        }

        // Function to find and print anti-diagonals
        ArrayList<ArrayList<Integer>> antiDiagonals = getAntiDiagonals(matrix, N);

        // Printing the anti-diagonals
        for (ArrayList<Integer> diagonal : antiDiagonals) {
            for (int num : diagonal) {
                System.out.print(num + " ");
            }
            System.out.println();
        }
    }

    private static ArrayList<ArrayList<Integer>> getAntiDiagonals(ArrayList<ArrayList<Integer>> matrix, int N) {
        ArrayList<ArrayList<Integer>> antiDiagonals = new ArrayList<>();

        // Collecting elements of anti-diagonals
        for (int d = 0; d < 2 * N - 1; d++) {
            ArrayList<Integer> currentDiagonal = new ArrayList<>();

            // Upper half of the matrix
            if (d < N) {
                for (int i = 0; i <= d; i++) {
                    currentDiagonal.add(matrix.get(i).get(d - i));
                }
            } else {
                // Lower half of the matrix
                for (int i = d - N + 1; i < N; i++) {
                    currentDiagonal.add(matrix.get(i).get(d - i));
                }
            }

            // Filling with zeros to make the row size consistent with N
            while (currentDiagonal.size() < N) {
                currentDiagonal.add(0);
            }

            // Adding the current diagonal to

 the result list
            antiDiagonals.add(currentDiagonal);
        }

        return antiDiagonals;
    }
}
```

---

### **Conclusion:**
This problem enhances understanding of matrix traversal in non-standard ways, particularly diagonally. It requires careful iteration and the ability to handle variable starting and ending points within the matrix. Additionally, it involves manipulating and preparing output in a specific format, which is a common requirement in software and algorithm development.