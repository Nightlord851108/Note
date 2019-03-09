# Longest Common Subsequence(LCS)

## Problem statement
Given two sequences, find the length of longest subsequence present in both of them.

It is a classic computer science problem, the basis of diff (a file comparison program that outputs the differences between two files), and has applications in bioinformatics.

Examples:
LCS for input Sequences “ABCDGH” and “AEDFHR” is “ADH” of length 3.
LCS for input Sequences “AGGTAB” and “GXTXAYB” is “GTAB” of length 4.

## Solution
The [naive solution](#naive-solution) for this problem is to generate all subsequences of both given sequences and find the longest matching subsequence. This solution is exponential in term of time complexity. Let us see how this problem possesses both important properties of a [Dynamic Programming (DP)](#dynamic-programming-solution) Problem.

### Naive solution
#### Optimal substructure
Let input sequences be X[0..m-1], Y[0..n-1].<br/>
Let L(X[0..m-1], Y[0..n-1]) be the length of LCS of X and Y.<br/>

if (X[m-1] == Y[n-1])<br/>
&nbsp;&nbsp;&nbsp;&nbsp; L(X[0..m-1], Y[0..n-1]) = 1 + L(X[0..m-2], Y[0..n-2])

else: <br/>
&nbsp;&nbsp;&nbsp;&nbsp; L(X[0..m-1], Y[0..n-1]) = MAX ( L(X[0..m-2], Y[0..n-1]), L(X[0..m-1], Y[0..n-2]) )

#### Overlapping subproblems
```
/* A Naive recursive implementation of LCS problem */
#include<bits/stdc++.h>

int max(int a, int b);

/* Returns length of LCS for X[0..m-1], Y[0..n-1] */
int lcs( char *X, char *Y, int m, int n, char *str)
{
    if (m == 0 || n == 0)
        return 0;
   if (X[m-1] == Y[n-1]) {
        int result = lcs(X, Y, m-1, n-1, str);
        str[result] = X[m-1];
        str[result+1] = '\0';
        return 1 + result;
   }
   else
      return max(lcs(X, Y, m, n-1, str), lcs(X, Y, m-1, n, str));
}

/* Utility function to get max of 2 integers */
int max(int a, int b)
{
    return (a > b)? a : b;
}

/* Driver program to test above function */
int main()
{
  char X[] = "AGGTAB";
  char Y[] = "GXTXAYB";

  int m = strlen(X);
  int n = strlen(Y);
  char str[max(m, n)];

  printf("Length of LCS is %d\n", lcs( X, Y, m, n, str) );
  printf("LCS subsequence is %s", str);

  return 0;
}
```

Output:
```
Length of LCS is 4
LCS subsequence is GTAB
```

Time complexity of the above naive recursive approach is O(2^n) in worst case and worst case happens when all characters of X and Y mismatch i.e., length of LCS is 0.

### Dynamic programming solution
This problem has Overlapping Substructure property and recomputation of same subproblems can be avoided by either using Memoization or Tabulation. Following is a tabulated implementation for the LCS problem.

```
/* Dynamic Programming C/C++ implementation of LCS problem */
#include<bits/stdc++.h>

int max(int a, int b);

/* Returns length of LCS for X[0..m-1], Y[0..n-1] */
int lcs( char *X, char *Y, int m, int n, char *str)
{
   int L[m+1][n+1];
   int i, j;

   /* Following steps build L[m+1][n+1] in bottom up fashion. Note
      that L[i][j] contains length of LCS of X[0..i-1] and Y[0..j-1] */
    for (i=0; i<=m; i++)
    {
        for (j=0; j<=n; j++)
        {
            if (i == 0 || j == 0)
                L[i][j] = 0;

            else if (X[i-1] == Y[j-1]) {
                int result = L[i-1][j-1];
                str[result] = X[i-1];
                str[result + 1] = '\0';
                L[i][j] = result + 1;
            }
            else
                L[i][j] = max(L[i-1][j], L[i][j-1]);
     }
   }

   /* L[m][n] contains length of LCS for X[0..n-1] and Y[0..m-1] */
   return L[m][n];
}

/* Utility function to get max of 2 integers */
int max(int a, int b)
{
    return (a > b)? a : b;
}

/* Driver program to test above function */
int main()
{
  char X[] = "AGGTAB";
  char Y[] = "GXTXAYB";

  int m = strlen(X);
  int n = strlen(Y);

  char str[max(m, n)];

  printf("Length of LCS is %d\n", lcs( X, Y, m, n, str) );
  printf("LCS subsequence is %s", str);
  return 0;
}

```
