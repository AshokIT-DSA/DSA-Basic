### **Identity Matrix Checker - Editorial**

## Difficulty: Easy

## Prerequisites: Matrices, Loops, Conditionals

### Problem Statement:
Participants need to create a program that can analyze a square matrix 'A' of dimensions 'N x N' and determine whether it is an identity matrix. An identity matrix is defined as a matrix where all the elements on the main diagonal are 1, and all other elements are 0.

### Detailed Explanation:

1. **Understanding the Task:**
   This problem requires a clear understanding of the structure of an identity matrix and the ability to efficiently traverse a matrix to check all elements against the identity matrix's conditions.

2. **Solution Approach:**
   We'll start by reading the matrix 'A'. Then, we iterate through every element of 'A', checking that each element satisfies the conditions of being an identity matrix:
   - Elements on the main diagonal (i.e., positions where row index equals column index) must be equal to 1.
   - All other elements (where row index does not equal column index) must be 0.
   If all these conditions are met throughout the entire matrix, we conclude that 'A' is an identity matrix.

3. **Problem Constraints:**
   - Matrix dimensions: 2 <= N <= 1000
   - Each matrix element 'A[i][j]' is either 0 or 1.
   
   These constraints indicate that the matrix can be large, requiring efficient processing. They also simplify checks, as elements are binary.

## Pseudo Code:

<pre><code>
read N
initialize matrix 'A' of dimensions N x N

for i = 0 to N-1 do:
    for j = 0 to N-1 do:
        if (i == j and A[i][j] != 1) or (i != j and A[i][j] != 0) then
            print "Not an Identity Matrix"
            exit
        end if
    end for
end for

print "Identity Matrix"
</code></pre>

### Time Complexity:
O(N^2), as the algorithm involves a nested loop that requires iterating through each element of the N x N matrix once. This quadratic time complexity is appropriate, considering the size constraints of 'N'.

### Space Complexity:
O(1), excluding the input space. The algorithm checks each element in place and does not require any additional significant space that grows with input size.

## Sample Code (Java):

```java
import java.util.Scanner;

public class IdentityMatrixChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N = scanner.nextInt();
        int[][] A = new int[N][N];

        // Reading the matrix
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                A[i][j] = scanner.nextInt();
            }
        }

        // Checking for identity matrix
        boolean isIdentity = true;
        for (int i = 0; i < N && isIdentity; i++) {
            for (int j = 0; j < N && isIdentity; j++) {
                if ((i == j && A[i][j] != 1) || (i != j && A[i][j] != 0)) {
                    isIdentity = false; // If any element does not meet the conditions, it's not an identity matrix
                }
            }
        }

        // Output based on identity check
        if (isIdentity) {
            System.out.println("Identity Matrix");
        } else {
            System.out.println("Not an Identity Matrix");
        }
    }
}
