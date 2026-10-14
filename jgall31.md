# Profile: Jazmin Gallardo

- **NetID:** jgall31
- **Major:** Kinesiology
- **Question that I chose from the memoization exercise:** Climbing stairs to reach the top
- **Link to the question article:** https://www.geeksforgeeks.org/dsa/count-ways-reach-nth-stair/ 
- **My solution:**


int countWaysRec(int n, int dp[]) {
    
    // Base Cases
    if (n == 0 || n == 1){
        return 1;
    }
    
    // if you already found the answer, quit the function
    if(dp[n] != -1){
        return dp[n];
    }
    
    return dp[n] = countWaysRec(n - 1, dp) + countWaysRec(n - 2, dp);
}

int countWays(int n){
    
    //make dp array that will store the results
    int* dp = (int*)malloc((n + 1) * sizeof(int));
    
    for (int i = 0; i <= n, i++){
        dp[i] = -1;
    }
    
    int result = countWaysRec(n, dp);
    free(dp);
    return result;
}
