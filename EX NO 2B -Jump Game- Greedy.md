
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 30.04.26
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm
1. Read input: Number of elements n. Array nums[] of size n, where each element represents the maximum jump length from that position.
2. Handle base cases: If n <= 1, no jump is needed → return 0. If nums[0] == 0, the end cannot be reached → return -1.
3. Initialize variables: jumps = 0 → to count the number of jumps made. currentReach = 0 → farthest index reachable with the current number of jumps. maxReach = 0 → farthest index reachable from all positions checked so far.
4. Iterate through the array (from index 0 to n-2): Update maxReach = max(maxReach, i + nums[i]) to find how far we can reach from index i.
5. If i == currentReach: Increment jumps (we’ve used one jump). Update currentReach = maxReach (update the boundary for the next jump). If currentReach >= n - 1, return jumps (end can be reached). If currentReach == i, return -1 (no further progress possible).
6. If the loop ends without reaching the last index, return -1.
7. Display the result: Print "Minimum jumps to reach last index: " followed by the number of jumps.


## Program:
```
/*
Program to implement Reverse a String
Developed by: SARISH VARSHAN V
Register Number:  212223230196
*/

import java.util.Scanner;

public class MinJumpToEnd {

    // Function to return minimum jumps to reach end
    public static int minimumJumps(int[] nums) {
        if(nums.length<=1) return 0;
        if(nums[0]==0) return -1;
        int jumps=0;
        int currentEnd=0;
        int farthest=0;
        for(int i=0;i<nums.length-1;i++){
            farthest=Math.max(farthest,i+nums[i]);
            if(i==currentEnd){
                jumps++;
                currentEnd=farthest;
            }
            if(currentEnd>nums.length-1) break;
            if(currentEnd==i) return -1;
        }
        return currentEnd>=nums.length-1?jumps:-1;
    }

    // Main method to handle input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}

```

## Output:
<img width="998" height="313" alt="image" src="https://github.com/user-attachments/assets/52d6846f-7072-4bff-a435-29f30bb67ee9" />



## Result:
The program successfully implemented and the expected output is verified.
