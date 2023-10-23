### **Find Good Pairs - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Hashing, Two-pointer Technique

### Problem Statement:
You are given an array of integers 'A' and a single integer 'B'. The task is to determine if there exists at least one good pair in the array. A pair (i, j) is considered good if 'i' is not equal to 'j', and the sum of A[i] and A[j] equals 'B'. You need to return a boolean indicating the existence of such a pair.

### Detailed Explanation:

1. **Understanding the Task:**
   We are tasked with finding whether there exists a pair of elements within the array 'A' such that their sum is equal to another given number 'B'. This problem is commonly known as the "two-sum" problem.

2. **Solution Approach:**
   The straightforward approach would involve a nested loop to go through each pair and check their sum. However, this is not the most efficient method. Instead, we can utilize a HashSet to store numbers we've already seen and look for the complement of the current element (i.e., B - A[i]) as we iterate through the array. 

   Alternatively, if the array is sorted or if we can afford to sort it, we could use a two-pointer technique to find if there's a pair that sums up to 'B'.

3. **Problem Constraints:**
   Given the constraints (1 <= N <= 10000 and 1 <= A[i], B <= 10000), the sorting approach and the HashSet approach should both work within the limits. However, the HashSet approach offers better time complexity.

## Pseudo Code for the HashSet approach:

<pre><code>
read N, A[N], B
create a HashSet
for each element 'el' in A do:
    if HashSet contains (B - el) then:
        print true
        exit
    end if
    add 'el' to the HashSet
end for
print false  // No pair found
</code></pre>

### Time Complexity:
The time complexity of the HashSet approach is O(N) because we go through the array once, and operations with the HashSet (both adding and checking for existence) are O(1) on average.

### Space Complexity:
O(N), since in the worst case, we will store all the elements of 'A' in the HashSet.

## Sample Code (Java):

```java
import java.util.HashSet;
import java.util.Scanner;

public class FindGoodPairs {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Read the array size
        int N = scanner.nextInt();
        int[] A = new int[N];

        // Read the array elements
        for (int i = 0; i < N; i++) {
            A[i] = scanner.nextInt();
        }

        // Read the target sum
        int B = scanner.nextInt();

        // Create a set to remember the numbers we've seen
        HashSet<Integer> seenNumbers = new HashSet<>();

        // Check each number against all previously seen numbers
        for (int number : A) {
            if (seenNumbers.contains(B - number)) {
                System.out.println("true");
                return;
            }
            seenNumbers.add(number);
        }

        // If we reached here, no good pair was found
        System.out.println("false");
    }
}
```

### Conclusion:
This problem illustrates a common pattern of using a HashSet to find complementary pairs, significantly reducing the time complexity compared to a brute-force approach. It demonstrates how space-time trade-offs can lead to more efficient solutions in problems involving pair sums or subarray sums.