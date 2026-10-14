# Profile: [Momen Alhejoj]

- **NetID:** [malhe]
- **Major:** [CS + Design]
- **Question that I chose from the memoization exercise:** [Count ways to reach the n'th stair]
- **Link to the question article:** [https://www.geeksforgeeks.org/dsa/count-ways-reach-nth-stair/]
- **My solution:**

// code modified by me using memo

int countWaysRec(int n, int memo[]) {
    
    if (n == 0 || n == 1) {
        return 1;
    }
    if (memo[n] != -1) {
        return memo[n];
    }
    
    return memo[n] = countWaysRec(n - 1, memo) + countWaysRec(n - 2, memo); 
}

int createMemo(int n) {
    
    int* memo = (int*) malloc((n + 1) * sizeof(int));
    
    for (int i = 0; i <= n; i++) {
        memo[i] = -1;
    }
    
    int result = countWaysRec(n, memo);
    free(memo);
    
    return result;
}