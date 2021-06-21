# Vaccine-filtering MEDIUM - python3


```python3

m,n=map(int,input().split())
 
vaccineFilter=[]
for i in range(m):
  vaccineFilter.append(list(map(int,input().split())))
  
for i in range(m):
  for j in range(n):
    if vaccineFilter[i][j]%2==1:
      vaccineFilter[i][j]=1
    else:
      vaccineFilter[i][j]=0
    if i>0 and j>0:
      vaccineFilter[i][j]+=vaccineFilter[i][j-1]+vaccineFilter[i-1][j]-vaccineFilter[i-1][j-1]
    elif j>0:
      vaccineFilter[i][j]+=vaccineFilter[i][j-1]
    elif i>0:
      vaccineFilter[i][j]+=vaccineFilter[i-1][j]
 
queryNo=int(input())
for i in range(queryNo):
  li,lj,ri,rj=map(int,input().split())
  li-=1
  lj-=1
  ri-=1
  rj-=1
  result=0
  if li>0 and lj>0:
    result+=vaccineFilter[ri][rj]-vaccineFilter[ri][lj-1]-vaccineFilter[li-1][rj]+vaccineFilter[li-1][lj-1]
  elif lj>0:
    result+=vaccineFilter[ri][rj]-vaccineFilter[ri][lj-1]
  elif li>0:
    result+=vaccineFilter[ri][rj]-vaccineFilter[li-1][rj]
  else:
    result+=vaccineFilter[ri][rj]
  print(result)

```
