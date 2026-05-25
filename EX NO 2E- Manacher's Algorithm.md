
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 30.04.26
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm
1. Input number of test cases T
2. Repeat the following steps for each test case: Read the input text. Read the input pattern. Initialize an empty list result to store the starting indices of matches. n = length of text m = length of pattern
3. Slide the pattern over the text: For each position i from 0 to n - m: Compare each character of pattern with the substring of text starting at index i.
4. Initialize j = 0. While j < m and text[i + j] == pattern[j], continue comparing. If all characters match (j == m), add index i to result.
5. Check if no match is found: If result is empty, add -1 to indicate that the pattern was not found.
6. Print all indices in result.

## Program:
```
/*
Program to implement Reverse a String
Developed by: SARISH VARSHAN V
Register Number:  212223230196
*/

import java.util.*;

public class PatternMatching {

    public static List<Integer> findPatternIndices(String text, String pattern) {
        List<Integer> indices = new ArrayList<>();
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
                indices.add(i);
            }
        }
        if (indices.isEmpty()) {
            indices.add(-1);
        }
        return indices;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int T = Integer.parseInt(scanner.nextLine()); 

        for (int t = 0; t < T; t++) {
            String text = scanner.nextLine();
            String pattern = scanner.nextLine();

            List<Integer> indices = findPatternIndices(text, pattern);
            for (int idx : indices) {
                System.out.print(idx + " ");
            }
            System.out.println();
        }

        scanner.close();
    }
}
```

## Output:
<img width="780" height="296" alt="image" src="https://github.com/user-attachments/assets/09fc63a2-b3e6-42db-8d27-0e3836d90075" />


## Result:
The program successfully implemented and the expected output is verified.
