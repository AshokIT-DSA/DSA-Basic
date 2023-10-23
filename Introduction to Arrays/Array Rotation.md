### **Array Rotation - Editorial**

## Difficulty: Easy

## Prerequisites: Arrays, Reverse operation, Mathematics

### Problem Statement:
Participants are presented with a task to rotate an array 'A' of size 'N' towards the right 'B' times and then output the resulting array. The rotation is such that elements shift rightward, and the last element cycles back around to the start of the array.

### Detailed Explanation:

1. **Understanding the Task:**
   We are given an array and an integer 'B', indicating the number of rightward rotations to perform on the array. While a simple approach would involve iterative shifting, this isn't efficient, especially for large 'N' or 'B'. The problem can be optimized using a clever array reversal strategy that accomplishes the rotation in a series of steps, significantly improving the performance.

2. **Solution Approach:**
   The proposed solution uses a different approach rather than traditional rotation. It strategically reverses portions of the array to achieve the same result as rotating. Firstly, it adjusts 'B' to avoid unnecessary full array rotations using the modulo operator ('B = B % N'). It then performs three specific reversals:
   
   - The first section of the array up to the 'N-B-1' index.
   - The remaining section from 'N-B' to the end.
   - The entire array.
   
   These reversals effectively rotate the array rightward 'B' times.

3. **Implementation Details:**
   The solution involves a 'swap' helper method that reverses the elements in a specific section of the array. It uses two pointers, starting and ending, that work towards each other, swapping the elements at their positions. The main function calculates the effective rotation, partitions the array into sections, and calls 'swap' for each.

## Pseudo Code:

```plaintext
Function main:
    Read N, B, A[N]
    B = B % N  // Normalize rotations greater than array size
    Reverse array section: 0 to N-B-1
    Reverse array section: N-B to N-1
    Reverse the entire array: 0 to N-1
    Print the modified array

Function swap (arr, start, end):
    while start is less than end:
        Swap elements at positions start and end
        Increment start, Decrement end
```

### Time Complexity:
The time complexity is O(N), irrespective of the number of rotations, as every element in the array is touched exactly twice during the reversal processes.

### Space Complexity:
The space complexity is O(1), as the rotation is done in place, using a constant amount of space for the reversal process.

## Sample Code (Java):

```java
public class Solution {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int b = sc.nextInt();
        b = b % n;  // Normalize the number of rotations
        int arr[] = new int[n];
        for(int i=0; i<n; i++) arr[i] = sc.nextInt();
        
        // Reverse sections of the array to achieve rotation
        swap(arr, 0, n-b-1);
        swap(arr, n-b, n-1);
        swap(arr, 0, n-1);
        
        // Output the result
        for(int i=0; i<n; i++) System.out.print(arr[i] + " ");
    }
    
    // Helper method to reverse a section of the array
    public static void swap(int[] arr, int s, int e) {
        while(s < e) {
            int temp = arr[s];
            arr[s] = arr[e];
            arr[e] = temp;
            s++;
            e--;
        }
    }
}
```

### Conclusion:
This problem showcases an innovative approach to array rotation, avoiding traditional element-by-element rotation. It demonstrates the utility of array reversal as an effective tool for in-place array modification, highlighting both its efficiency and its low space requirement. This method is particularly advantageous for scenarios requiring multiple rotations or dealing with large data sets.