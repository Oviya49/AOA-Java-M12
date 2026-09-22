# EX 2D Pattern Matching using Naive Approach.
## DATE:12/8/26
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12
## Algorithm
1. Start
2. Read the input string text and the pattern to be searched.
3. Find the lengths of both strings:
n = length of text
m = length of pattern
4. Loop through the text from index i = 0 to i <= n - m:
5. For each position i, compare every character of the pattern with the corresponding character in the text.
6. If any character does not match, break out of the inner loop.
7. If all characters of the pattern match (j == m), print the index i where the pattern starts in the text.
8. Continue checking until the end of the text.
9. End

## Program:
```
Developed by: Oviya N 
Register Number:  212223040140
```

```
import java.util.Scanner;

public class NaivePatternSearch {

    public static void search(String text, String pattern) {
        int n = text.length();
        int m = pattern.length();

        for (int i = 0; i <= n - m; i++) {
            int j;
            for (j = 0; j < m; j++) {
                if (text.charAt(i + j) != pattern.charAt(j)) {
                    break;
                }
            }
            if (j == m) {
                System.out.println("Pattern found at index " + i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //System.out.print("Enter the text: ");
        String text = scanner.nextLine();

        //System.out.print("Enter the pattern: ");
        String pattern = scanner.nextLine();

        search(text, pattern);

        scanner.close();
    }
}
```
## Output:

<img width="1359" height="419" alt="image" src="https://github.com/user-attachments/assets/b6bacddf-065f-42cd-ad2f-27abeb83764e" />


## Result:
The program successfully implemented and the expected output is verified.
