# Sequence-2,3,5 Python3


```python3

testcase=int(input())
for _ in range(testcase):
    length=int(input())
    array=list(map(int,input().split()))
 
    total=1
    for num in array:
        total=(total*(num%10))%10
 
    if total==2 or total==3 or total==5:
        print("YES")
    else:
        print("NO")

```
