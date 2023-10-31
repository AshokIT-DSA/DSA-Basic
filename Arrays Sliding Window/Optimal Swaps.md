### **Optimal Swaps - Editorial**

---

## **Difficulty: Medium**

---

## **Prerequisites:**
- Arrays
- Sliding Window Technique

---

### **Problem:**
The task is to determine the minimum number of swaps needed to group all numbers less than or equal to a given value, B, together in an array.

---

### **Approach:**
The problem can be solved efficiently using the **sliding window technique**. Here's the detailed approach:

1. **Count the number of "good" elements**: The first step is to count the number of elements in the array which are less than or equal to `B`. Let's call these "good" elements. This will also be the size of the window we'll use in the sliding window technique.

2. **Count the number of "bad" elements in the initial window**: We'll start by counting the number of elements which are greater than `B` in the first window (i.e., the first "good" number of elements). We'll call these "bad" elements.

3. **Slide the window & Update the count of "bad" elements**: Now, we'll slide our window through the array. For each movement, we check the outgoing element (from the left) and the incoming element (from the right). If the outgoing element was bad, we decrease our bad count by 1. If the incoming element is bad, we increase our bad count by 1. 

4. **Keep track of minimum "bad" elements**: As we're sliding the window, we'll keep track of the minimum count of bad elements we've seen. This minimum count represents the number of swaps needed. Why? Because for the optimal position of the window, the number of "bad" elements inside it is exactly the number of swaps needed to move the "good" elements together.

### **Why does this work?**
The idea behind the approach is that the optimal solution will have a continuous sequence of "good" elements in the array. By using a sliding window of size equal to the number of "good" elements, we're effectively trying all possible placements of this sequence in the array. The number of "bad" elements in any such placement is the number of swaps needed to achieve that placement, and thus, by minimizing this, we get the solution.

### **Algorithm:**
```plaintext
Begin
    Read N, B and the array A

    Initialize "good" as the count of elements <= B
    Initialize "bad" as the count of elements > B in the first "good" elements

    Set minSwaps as "bad"

    Slide the window of size "good" through the array:
        Check the outgoing and incoming elements
        Update the count of "bad" elements
        Update minSwaps to the minimum seen "bad" count

    Print minSwaps
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N)
  - The solution iterates over the array twice (once for counting good elements and once for sliding the window), making the time complexity linear or O(N).

- **Space Complexity:** O(1)
  - The solution doesn't use any additional space proportional to the size of the input, so the space complexity is O(1).

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int b = sc.nextInt();
        ArrayList<Integer> A = new ArrayList<>();
        for(int i=0;i<n;i++) A.add(sc.nextInt());
        
        System.out.println(solve(A,b));
    }
    
    public static int solve(ArrayList<Integer> A, int B) {
        int n = A.size();
        int good = 0;

        // Count the number of "good" elements
        for (int i = 0; i < n; i++) {
            if (A.get(i) <= B) {
                good++;
            }
        }

        // Count the number of "bad" elements in the initial window
        int bad = 0;
        for (int i = 0; i < good; i++) {
            if (A.get(i) > B) {
                bad++;
            }
        }

        int minSwaps = bad;

        // Slide the window through the array
        for (int i = 0, j = good; j < n; i++, j++) {
            if (A.get(i) > B) {
                bad--;
            }
            if (A.get(j) > B) {
                bad++;
            }
            minSwaps = Math.min(minSwaps, bad);
        }

        return minSwaps;
    }
}
```

---

### **Conclusion:**
The problem illustrates how a seemingly complex problem can be reduced to a simple one using the sliding window technique. By sliding a window and counting the number of elements that don't fit the criteria, we're able to find the optimal solution in linear time.