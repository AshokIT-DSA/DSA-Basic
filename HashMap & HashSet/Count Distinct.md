# **Editorial: Count Distinct**

## **Difficulty: Easy**

## **Prerequisites:**
- Arrays
- Hashing (Set)
- Iteration

---

### **Problem Statement:**
You are given an array 'A' consisting of 'N' integers. Your goal is to efficiently determine and print the count of distinct elements in this array.

---

### **Detailed Explanation:**

1. **Understanding the Task:**
   The problem task is clear cut: to count the number of distinct elements in the array. A distinct element is one that appears at least once, irrespective of how many times it appears.

2. **Solution Approach:**
   The optimal approach to determine distinct elements in an array is to use a set data structure. Sets are collections where each item is unique. By adding all elements of the array to a set, we can easily determine the count of distinct elements. The size of the set after all insertions will give us the count of distinct elements.

3. **Problem Constraints:**
   With 'N' being as large as 10<sup>5</sup> and individual elements up to 10<sup>8</sup>, our solution needs to be efficient. The set data structure allows for typically O(1) operations for insertion and membership checks, making this approach ideal for our constraints.

---

### Pseudo Code:

<pre><code>
Read the integer 'N'
Read the array 'A' of integers of size 'N'

Create a new empty set 'distinctElements'

for each 'element' in 'A':
    Add 'element' to 'distinctElements'

Print the size of 'distinctElements'
</code></pre>

### Complexity Analysis:

**Time Complexity:** O(N) - Generally, set operations (like insertion) are O(1) on average. Thus, the time taken to insert 'N' elements is O(N). However, some set implementations can have O(log N) complexity for certain operations, but even in such cases, the overall time complexity is reasonable given our constraints.

**Space Complexity:** O(N) - In a situation where all elements are distinct, the set will contain all 'N' elements of the array.

### Sample Code (Java):

```java
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;

public class CountDistinct {
    public static void main(String[] args) {
        // Scanner object for input
        Scanner scanner = new Scanner(System.in);

        // Reading the size of the array
        int N = scanner.nextInt();

        // Set to store distinct elements
        Set<Integer> distinctElements = new HashSet<>();

        // Reading array elements
        for (int i = 0; i < N; i++) {
            // Add element to the set
            distinctElements.add(scanner.nextInt());
        }

        // The set's size is the number of distinct elements
        System.out.println(distinctElements.size());
    }
}
