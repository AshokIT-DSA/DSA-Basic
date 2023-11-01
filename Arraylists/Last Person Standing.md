### **Last Person Standing - Editorial**

---

## **Difficulty: Easy**

---

## **Prerequisites:**
- Arrays
- Simulation
- Josephus Problem

---

### **Problem:**
The problem requires determining the position of the last person standing in a simulated killing game where each person kills the one to their immediate clockwise direction in a circle. This is a variation of the classic Josephus problem.

---

### **Approach:**
The solution to this problem can be approached by simulating the process of elimination. However, instead of brute force, we can recognize this as a famous problem in computer science and mathematics known as the Josephus problem, which has a well-known solution using recursion or iteration.

The approach implemented here uses an ArrayList to simulate the circle and continuously removes the next person in the circle until only one person remains. This method, while intuitive, is not the most efficient for large N.

---

### **Algorithm:**
```plaintext
Begin
    Read integer N

    Create an ArrayList al and fill it with numbers from 1 to N

    Initialize pointer p to 0

    While the size of al is greater than 1
        Calculate next person's index (p + 1) modulo the size of al
        Remove the person at the next index from al
        Update pointer p to the next index

    The last remaining person's number in al is the answer

    Print the last remaining number
End
```

### **Complexity Analysis:**
- **Time Complexity:** O(N^2)
  - In each step of the while loop, the `remove` operation of ArrayList takes O(N) time, and since there are N such operations, the time complexity is O(N^2).
- **Space Complexity:** O(N)
  - We maintain an ArrayList of size N to store the people in the circle.

---

## **Java Solution:**
```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println(solve(sc.nextInt()));
    }

    public static int solve(int A) {
        ArrayList<Integer> al = new ArrayList<>();
        for (int i = 1; i <= A; i++) al.add(i);

        int p = 0;
        while (al.size() > 1) {
            int next = (p + 1) % al.size();
            al.remove(next);
            p = (next % al.size()); // update pointer to the next person's index after removal
        }
        return al.get(0);
    }
}
```

---

### **Conclusion:**
The given problem is a twist on the classic Josephus problem, which is a theoretical problem related to a certain counting-out game. While the provided solution correctly simulates the problem, for large N, it would be inefficient. A more efficient solution involves understanding the underlying pattern of the Josephus problem and applying a mathematical formula or using a linked list to simulate the elimination process with a time complexity of O(N).