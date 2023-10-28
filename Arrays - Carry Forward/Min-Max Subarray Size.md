### **Min-Max Subarray Size - Editorial**

---

## **Difficulty: Medium**

---

## **Prerequisites:**
- Arrays
- Iteration
- Min-Max

---

### **Problem Statement:**
This problem requires determining the size of the smallest subarray that includes both the maximum and minimum values of a given array A. The challenge is not only finding the maximum and minimum elements but also identifying the shortest range within which these two elements coexist.

---

### **Solution Approach:**
The solution involves iterating through the array to find the positions of the maximum and minimum values and then determining the shortest distance between any two occurrences of these values. The strategy ensures that we consider all possible subarrays containing the max and min elements.

Here's a step-by-step breakdown of the method used in the solution:

1. **Edge Case Check:**
   - If the array size is less than or equal to 1, the smallest subarray is the array itself.

2. **Finding Min and Max:**
   - Find the minimum and maximum values in the array using collection functions. This step involves scanning the entire array once.

3. **Initialization:**
   - Initialize variables to keep track of the latest positions of the minimum and maximum values encountered during iteration (`minIndex` and `maxIndex`).
   - Initialize the `minMaxSubarraySize` to the maximum possible integer value. It represents the size of the current smallest subarray containing both extremes.

4. **Array Traversal:**
   - Traverse the array. For each element, check if it equals the min or max values.
   - Update the respective indices (`minIndex` or `maxIndex`) when occurrences are found.
   - Each time you update an index, calculate the size of the subarray defined by the current min and max positions. Update `minMaxSubarraySize` if you find a smaller subarray.

5. **Result Output:**
   - After completing the array traversal, the variable `minMaxSubarraySize` will hold the size of the smallest subarray containing both the minimum and maximum values. Return this value.

### **Pseudo Code:**
```plaintext
Function FindMinMaxLengthSubarray
    Read the array A
    Find minimum and maximum values in A
    Initialize minIndex, maxIndex, and minMaxSubarraySize

    If minimum equals maximum
        Return 1

    For each element in A
        Update minIndex or maxIndex if element is min or max
        Calculate subarray size from minIndex to maxIndex
        Update minMaxSubarraySize if current is smaller

    Return minMaxSubarraySize
EndFunction
```

### **Time Complexity:**
The solution has a time complexity of O(N) because it involves a single traversal through the array, where N is the number of elements in the array.

### **Space Complexity:**
The space complexity of the solution is O(1), as there is no additional space used that grows with input size. The variables for tracking indices and the min-max subarray size require constant space.

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        /* Enter your code here. Read input from STDIN. Print output to STDOUT. Your class should be named Solution. */
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Integer> A = new ArrayList<>();
        for(int i = 0; i < n; i++) A.add(sc.nextInt());

        System.out.println(solve(A));
    }

    public static int solve(ArrayList<Integer> A) {
        int n = A.size();
        if (n <= 1) {
            return n;
        }

        int min = Collections.min(A);
        int max = Collections.max(A);

        int minIndex = -1;
        int maxIndex = -1;
        int minMaxSubarraySize = Integer.MAX_VALUE;

        if (min == max) {
            return 1; // All elements are the same
        }

        for (int i = 0; i < n; i++) {
            if (A.get(i) == min) {
                minIndex = i;
                if (maxIndex != -1) {
                    minMaxSubarraySize = Math.min(minMaxSubarraySize, Math.abs(maxIndex - minIndex) + 1);
                }
            } else if (A.get(i) == max) {
                maxIndex = i;
                if (minIndex != -1) {
                    minMaxSubarraySize = Math.min(minMaxSubarraySize, Math.abs(maxIndex - minIndex) + 1);
                }
            }
        }

        return minMaxSubarraySize;
    }
}
```

---

### **Conclusion:**
This problem emphasizes the importance of considering the positions of elements within an array, not just their values. The solution efficiently computes the smallest subarray that contains both the maximum and minimum values by tracking the positions of

 these extremes during a single traversal through the array.