# Can You Win the Challenge

```Python3
def factorial(n):
    if n==1:
        return 1
    else:
        return n*factorial(n-1)

n=int(input())
fact=factorial(n)
print(fact%(10**9+7))
```
