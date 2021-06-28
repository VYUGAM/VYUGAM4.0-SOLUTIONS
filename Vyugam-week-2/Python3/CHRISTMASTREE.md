# CHRISTMAS TREE - MEDIUM

```python3

testcase=int(input())
for _ in range(testcase):
	n=int(input())
	if n>=1:
        print("1")
	if n>=2:
    	print("1 1")
	tree=[1,1]
 
	for i in range(n-2):
    	pos=(i+2)//2
    	tree.insert(pos,0)
        tree[pos]=tree[pos-1]+tree[pos+1]
 
    	for j in range(pos+1,i+2):
            tree[j]+=tree[j+1]
    	for j in range(pos-1,0,-1):
            	tree[j]+=tree[j-1]
            	
    	for number in tree:
            print(number,end=" ")
    	print()


```
