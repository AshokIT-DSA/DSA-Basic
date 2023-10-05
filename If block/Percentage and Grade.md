### **Calculate Student's Grade - Editorial**
## Difficulty:- Easy

## Prerequisite:- Basic Arithmetic, If-Else 

### Problem statement:-
You're given five numbers, namely A, B, C, D, and E, which represent the marks of a student in five subjects. Each subject's marks are out of 100. Your task is to:
1. Calculate the percentage of the student.
2. Determine the grade based on the calculated percentage.

### Short Explanation:-
1. Calculate the percentage by summing up all the marks and then dividing by the total maximum marks (which is 500, as each subject is out of 100).
2. Assign a grade based on the calculated percentage using conditional statements.

### Detailed Explanation:-

**Step 1: Calculating Percentage**  
First, you need to calculate the total marks the student has achieved, which is `A + B + C + D + E`. Since each subject is out of 100, the maximum marks are 500. Thus, the percentage is calculated as:

\[ \text{Percentage} = \left(\frac{A + B + C + D + E}{500}\right) \times 100 \]

**Step 2: Assigning Grade**  
Based on the calculated percentage, assign a grade using the given conditions.

## Pseudo Code

<pre><code>
function calculateGrade(A, B, C, D, E) {
    total_marks = A + B + C + D + E;
    percentage = (total_marks / 500) * 100;

    if (percentage >= 90) {
        grade = 'A';
    } else if (percentage >= 80) {
        grade = 'B';
    } else if (percentage >= 70) {
        grade = 'C';
    } else if (percentage >= 60) {
        grade = 'D';
    } else if (percentage >= 40) {
        grade = 'E';
    } else {
        grade = 'F';
    }

    print("Percentage: " + percentage + "%");
    print("Grade: " + grade);
}
</code></pre>

### Time Complexity:-
The overall complexity of the `calculateGrade` function is O(1), as all operations are performed in constant time.

### Space Complexity:- 
O(1), as no extra space is used, regardless of the input.

## Java Code:

```java
import java.util.Scanner;

public class StudentGrade {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("Enter marks for five subjects (out of 100 each):");
        int A = scanner.nextInt();
        int B = scanner.nextInt();
        int C = scanner.nextInt();
        int D = scanner.nextInt();
        int E = scanner.nextInt();

        int total_marks = A + B + C + D + E;
        double percentage = (double) total_marks / 5;

        char grade;

        if (percentage >= 90) {
            grade = 'A';
        } else if (percentage >= 80) {
            grade = 'B';
        } else if (percentage >= 70) {
            grade = 'C';
        } else if (percentage >= 60) {
            grade = 'D';
        } else if (percentage >= 40) {
            grade = 'E';
        } else {
            grade = 'F';
        }

        System.out.println("Percentage: " + percentage + "%");
        System.out.println("Grade: " + grade);
    }
}
```

Students can run the above code, input their marks for each subject when prompted, and then see their overall percentage and corresponding grade.