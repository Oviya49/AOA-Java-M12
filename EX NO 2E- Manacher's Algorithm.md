# EX 2E Pattern Matching using KMP Algorithm.

## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Start
2. Read the input string s.
3. If the string is empty, return an empty result.
4. Preprocess the string by inserting a special character (e.g., #) between each letter and at both ends to handle even-length palindromes uniformly.
Example: "abba" → "#a#b#b#a#"
5. Initialize variables:
p[] → array to store palindrome radii centered at each position
center = 0 and right = 0 → current center and right boundary of the known palindrome
maxLen = 0 and centerIndex = 0 → track longest palindrome found so far
For each position i in the processed string:
6. Find the mirror position: mirror = 2 * center - i
7. If i < right, set p[i] = min(right - i, p[mirror]).
8. Expand around i while characters on both sides match (t[a] == t[b]).
9. Update p[i] for every successful expansion.
10. If i + p[i] > right, update center = i and right = i + p[i].
11. If p[i] > maxLen, update maxLen and centerIndex.
12. Compute the starting index of the palindrome in the original string:
13. start = (centerIndex - maxLen) / 2
14. Extract and return the substring from start to start + maxLen.
15. Print the longest palindromic substring.
16. End 


## Program:
Developed by: V Mythili 
Register Number:  212223040123

```
import java.util.Scanner;

public class LongestPalindromeManacher {

    public static String longestPalindrome(String s) {
        if (s == null || s.length() == 0) return "";

        StringBuilder t = new StringBuilder();
        t.append('#');
        for (int i = 0; i < s.length(); i++) {
            t.append(s.charAt(i));
            t.append('#');
        }

        int n = t.length();
        int[] p = new int[n];
        int center = 0, right = 0;
        int maxLen = 0, centerIndex = 0;

        for (int i = 0; i < n; i++) {
            int mirror = 2 * center - i;
            if (i < right) {
                p[i] = Math.min(right - i, p[mirror]);
            }

            int a = i + (1 + p[i]);
            int b = i - (1 + p[i]);
            while (a < n && b >= 0 && t.charAt(a) == t.charAt(b)) {
                p[i]++;
                a++;
                b--;
            }

            if (i + p[i] > right) {
                center = i;
                right = i + p[i];
            }

            if (p[i] > maxLen) {
                maxLen = p[i];
                centerIndex = i;
            }
        }

        int start = (centerIndex - maxLen) / 2;
        return s.substring(start, start + maxLen);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        String result = longestPalindrome(input);
        System.out.println("Longest Palindromic Substring: " + result);
        sc.close();
    }
}
```
## Output:

<img width="1664" height="513" alt="image" src="https://github.com/user-attachments/assets/962deace-04d3-466a-a364-d7e407c62dab" />


## Result:
The program successfully implemented and the expected output is verified.
