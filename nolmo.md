# Profile: Noah Olmos

- **NetID:** nolmo
- **Major:** Computer Science + Design
- **Question that I chose from the memoization exercise:** "Ways to Reach the n'th Stair"
- **Link to the question article:** (https://www.geeksforgeeks.org/dsa/count-ways-reach-nth-stair/)
- **My solution:**

\```

Paste your C code here. It should contain the comments you added when trying to solve.

Solution from geeksforgeeks.org (modified by me):

int countWaysRec(int n, int memo[]) {

    // Base cases
    if (n == 0 || n == 1) {
        return 1;
    }

    // if the result for this subproblem is 
    // already computed then return it
    if (memo[n] != -1) {
        return memo[n];
    }

    return memo[n] = countWaysRec(n - 1, memo) + countWaysRec(n - 2, memo); 
}

int countWays(int n) {

    // dp array to store the results
    int* memo = (int*)malloc((n + 1) * sizeof(int));
    for (int i = 0; i <= n; i++) {
        memo[i] = -1;
    }

    int result = countWaysRec(n, memo);
    free(memo);
    return result;
}

\```