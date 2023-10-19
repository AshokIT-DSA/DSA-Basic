# **Editorial: Count Unique**

## **Difficulty: Easy**

## **Prerequisites:**
- Arrays
- Hashing (Set)
- Iteration

---

### **Problem Statement:**
You have an array 'A' consisting of 'N' integers. Your task is to efficiently count how many unique elements are present in this array and print this count.

---

### **Detailed Explanation:**

1. **Understanding the Task:**
   The problem is straightforward in that you need to identify the count of distinct/unique elements in the given array. An element that appears more than once should be counted only once.

2. **Solution Approach:**
   A simple and efficient approach to solve this problem is by using a set data structure. Sets are collections of items where each element is unique. By inserting all elements of the array into a set, we automatically filter out duplicates. The size of the set will then give us the count of unique elements.

3. **Problem Constraints:**
   With 'N' up to 10<sup>5</sup> and individual elements within the range of 10<sup>8</sup>, we must handle large inputs, making the efficiency of our solution crucial. Fortunately, inserting items into a set and checking for membership is generally efficient, allowing this approach to work well within the given constraints.

---

### Pseudo Code:

<pre><code>
Read the integer 'N'
Read the array 'A' of integers of size 'N'

Create a new empty set 'uniqueElements'

for each 'element' in 'A':
    Add 'element' to 'uniqueElements'

Output the size of 'uniqueElements'
</code></pre>

### Complexity Analysis:

**Time Complexity:** O(N) - Since set operations in many languages are typically O(1) on average, the time to insert 'N' elements is O(N). There can be cases where the time complexity of set operations can go up to O(log N) for certain implementations, but even in such scenarios, the overall complexity remains manageable for our constraints.

**Space Complexity:** O(N) - In the worst case, if all elements are unique, the set will contain all 'N' elements from the array.

### Sample Code (Java):

```java
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;

public class CountUnique {
    public static void main(String[] args) {
        // Scanner object for taking input from standard input
        Scanner scanner = new Scanner(System.in);

        // Reading the size of the array
        int N = scanner.nextInt();

        // Set to store unique elements
        Set<Integer> uniqueElements = new HashSet<>();

        // Reading array elements
        for (int i = 0; i < N; i++) {
            // Add element to the set
            uniqueElements.add(scanner.nextInt());
        }

        // The size of the set is the number of unique elements
        System.out.println(uniqueElements.size());
    }
}
