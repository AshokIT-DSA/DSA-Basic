### **Find Leaders in an Array - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Iteration
- List manipulation

---

### **Problem Statement:**
You're given an array of integers, and your task is to identify all the 'leaders' in the array. A leader is an element with no elements greater than it to its right. Consequently, the rightmost element is always a leader. The challenge is to find these leaders and return them in the same order as they appear in the input array.

---

### **Approach:**
The solution is straightforward, involving a single backward traversal through the array. This traversal compares each element with a running maximum (or the current leader), which gets updated each time we find a new leader.

---

### **Procedure:**

1. **Initialization:**
   - If the array is empty, immediately return an empty list of leaders.
   - Initialize the 'maxRight' variable with the last element of the array, considering it as the initial leader since there are no elements to its right.

2. **Backward Traversal:**
   - Starting from the second-to-last element, move leftward through the array.
   - Compare each element with 'maxRight'. If the current element is greater, it's a new leader. In this case, update 'maxRight' and add the new leader to your list of leaders.

3. **Reversing the List:**
   - The list of leaders will be in reverse order due to the backward traversal of the array. To match the order in the input array, you need to reverse this list.
   - You can do this by creating a new list and filling it with the elements from the original list of leaders in reverse order.

4. **Conclusion:**
   - Return the reversed list, now containing all leaders in their original order from the input array.

---

### **Pseudocode:**
```plaintext
Begin
    - Initialize the leaders list
    - Set maxRight as the last element of the input array
    - Add maxRight to the leaders list

    For each element in the array, starting from the second-to-last and moving backward:
        If the current element is greater than maxRight
            Add it to the leaders list
            Update maxRight with the current element
        End If
    End For

    Reverse the leaders list to get the original order
    Return the reversed list
End
```

---

### **Complexities Analysis:**

- **Time Complexity:** The algorithm requires a single traversal through the array, leading to a time complexity of O(N), where N is the number of elements in the array.

- **Space Complexity:** The space complexity is also O(N) since, in the worst-case scenario, every element might be a leader, requiring space in the 'leaders' list.

---

## **Java Implementation:**

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Integer> A = new ArrayList<>();
        for(int i = 0; i < n; i++) A.add(sc.nextInt());

        // Find and print leaders
        ArrayList<Integer> leaders = findLeaders(A);
        for(int num : leaders) {
            System.out.print(num + " ");
        }
    }
    
    private static ArrayList<Integer> findLeaders(ArrayList<Integer> A) { 
        ArrayList<Integer> leaders = new ArrayList<>();
        
        // Initialize the last element as leader
        int maxRight = A.get(A.size() - 1);
        leaders.add(maxRight);

        // Traverse the list from right to left and find leaders
        for (int i = A.size() - 2; i >= 0; i--) {
            if (A.get(i) > maxRight) {
                maxRight = A.get(i);
                leaders.add(maxRight);
            }
        }

        // Reverse the list of leaders to maintain the original sequence
        Collections.reverse(leaders);
        return leaders;
    }
}
```

---

### **Conclusion:**

This task tests your array manipulation and iteration skills, particularly backward traversal and in-place list reversal. The efficient solution avoids extra space for two arrays and minimizes passes through the array, providing a streamlined approach suitable for larger input sizes.