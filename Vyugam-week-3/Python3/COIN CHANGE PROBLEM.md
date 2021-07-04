# Coin Change Problem

```Python3
def findPossibleWays(s,m,n):
    if n==0:
        return 1
    if n<0:
        return 0
    if m<=0 and n>=1:
        return 0
    return findPossibleWays(s,m-1,n) + findPossibleWays(s,m,n-s[m-1])

n,m=map(int,input().split())
s=list(map(int,input().split()))
res=findPossibleWays(s,m,n)
print(res)
```
