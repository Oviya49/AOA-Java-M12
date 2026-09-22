# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 3/8/2026
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm
1.Start the program.
 Read the number of children n and their greed factors array g[], then read the number of cookies m and their sizes array s[].

2.Sort both arrays — g[] (children’s greed) and s[] (cookie sizes) in ascending order.

3.Initialize two pointers:
i = 0 (for children) and j = 0 (for cookies).

4.Iterate while both pointers are valid:

If the current cookie s[j] can satisfy the current child’s greed g[i] (s[j] >= g[i]), assign the cookie and move to the next child (i++).

Move to the next cookie (j++) in all cases.

5.Display the result:
Print the total number of content (satisfied) children i and stop the program.

## Program:
```
Developed by: OVIYA N
Register Number: 212223040140
```

```

import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        // Type Your Logic Here.
        Arrays.sort(g);
        Arrays.sort(s);
        int i=0,j=0;
        while(i<g.length && j<s.length){
            if(s[j]>=g[i])i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}

```

## Output:
<img width="322" height="331" alt="image" src="https://github.com/user-attachments/assets/1325c7dd-56c4-41ec-af92-028b3eb3df0c" />


## Result:
The program successfully print all the numbers from 1 to N. 
