# 01 Knapsack Problem
```Python3
def knapSack(C,weight,value,n):
    dp=[0 for i in range(C+1)]
    for i in range(1,n+1):
        for c in range(C,0,-1):
            if weight[i-1]<=c:
                dp[c]=max(dp[c],dp[c-weight[i-1]]+value[i-1])
    return dp[C]

n,c=map(int,input().split())
value=list(map(int,input().split()))
weight=list(map(int,input().split()))
print(knapSack(c,weight,value,n))
```
