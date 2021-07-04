# 0-1 Knapsack problem - MEDIUM

```c++
# include<bits/stdc++.h>
using namespace std;
// Recursion with memoization => Top down DP
int memo[1000][20000];
 
// Constraints
// n
// C
int knapsack(int wt[], int val[], int C, int n){
    // Base condition
    if(C==0 || n==0){
        return 0;
    }
    
    // memoization
    if(memo[n][C]!=-1){
        return memo[n][C];
    }
    
    // Recursive conditions
    if(wt[n-1] <= C){
        return memo[n][C] = max(
            val[n-1] + knapsack(wt, val, C-wt[n-1], n-1),
            knapsack(wt, val, C, n-1)
        );
    }
    else if(wt[n-1] > C){
        return memo[n][C] = knapsack(wt, val, C, n-1);
    }
}
int main(){
    // C = capacity of the knapsack
    // n - no of items
    // wt[] - weight of the item
    // val[] - value of the item
    int C,n;
    cin>>n;
    cin>>C;
    int val[n+1],wt[n+1];
    for(int i=0;i<n;i++){ cin>>val[i]; }
    for(int i=0; i<n;i++){ cin>>wt[i]; }
 
 	memset(memo,-1,sizeof(memo));
    cout<<knapsack(wt, val, C, n);
    return 0;
}


```

