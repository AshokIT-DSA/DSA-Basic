### **Generate Spiral Matrix - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Loops
- Simulation

---

### **Problem:**
The goal is to generate an `N` x `N` matrix with elements from `1` to `N^2` arranged in a spiral order, starting from the top left corner and moving inwards in a clockwise direction.

---

### **Approach:**
The problem can be solved by simulating the process of filling the matrix in a spiral order. Here's the step-by-step approach:

1. **Initialize Boundaries**: Set up boundaries for the top (`t`), bottom (`b`), left (`l`), and right (`r`) sides of the matrix to keep track of the edges of the spiral.

2. **Initialize Matrix**: Create an `N` x `N` matrix and initialize all elements to `0`.

3. **Fill the Matrix in a Spiral**: Using a while loop, move along the matrix in a spiral pattern - right across the top, down the right side, left across the bottom, and up the left side - filling in values as you go. After completing each side of the border, adjust the corresponding boundary.

4. **Update Values**: The value to insert starts at `1` and ends at `N^2`. Increment the value after each insertion.

5. **Continue Until Done**: Continue the spiral motion until the `top` boundary is greater than the `bottom`, or the `left` boundary is greater than the `right`.

6. **Complete Matrix**: By the end, the matrix will be filled with elements from `1` to `N^2` in a spiral pattern.

### **Algorithm:**
```plaintext
Begin
    Read integer N

    Initialize matrix of size N x N to 0

    Set boundaries t = 0, b = N-1, l = 0, r = N-1
    Initialize value to fill val = 1

    While (t <= b AND l <= r)
        Fill the top row from left to right
        Increment top boundary

        Fill the right column from top to bottom
        Decrement right boundary

        Fill the bottom row from right to left (if top <= bottom)
        Decrement bottom boundary

        Fill the left column from bottom to top (if left <= right)
        Increment left boundary

        Increment val each time a cell is filled

    Return the filled matrix
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N^2)
  - The matrix is filled in a single pass with a simple nested loop structure, so the complexity is O(N^2), where `N` is the size of the matrix.

- **Space Complexity:** O(N^2)
  - The space used is the output matrix of size `N` x `N`, so the space complexity is O(N^2).

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<ArrayList<Integer>> res = generateMatrix(n);
            
        for(int i=0; i<res.size(); i++) {
            for(int j=0; j<res.get(i).size(); j++) {
                System.out.print(res.get(i).get(j) + " ");
            }
            System.out.println();
        }
    }
    
    public static ArrayList<ArrayList<Integer>> generateMatrix(int N) {
        int t = 0, b = N-1, l = 0, r = N-1;
        ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();
        
        for(int i = 0; i < N; i++) {
            ArrayList<Integer> row = new ArrayList<>(Collections.nCopies(N, 0));
            matrix.add(row);
        }
        
        int val = 1;
        while(t <= b && l <= r) {
            for(int i = l; i <= r; i++) matrix.get(t).set(i, val++);
            t++;
            for(int i = t; i <= b; i++) matrix.get(i).set(r, val++);
            r--;
            if(t <= b) {
                for(int i = r; i >= l; i--) matrix.get(b).set(i, val++);
                b--;
            }
            if(l <= r) {
                for(int i = b; i >= t; i--) matrix.get(i).set(l, val++);
                l++;
            }
        }
        
        return matrix;
    }
}
```

---

### **Conclusion:**
This problem highlights the importance of simulating the filling process and carefully managing boundaries within the matrix to create the desired pattern. The provided Java solution follows a methodical approach to fill the matrix in the required spiral order.