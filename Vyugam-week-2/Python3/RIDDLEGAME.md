# RIDDLE GAME - EASY

```python3

testcase=int(input())
for _ in range(testcase):
	size=int(input())
	binaryString=input()
	integerValue=0
	for i in range(size-1,-1,-1):
    	if binaryString[i]=='1':
        	integerValue+=2**(size-i-1)
	print(integerValue)

```
