# HELP JOE - MEDIUM

```python3
String=input()
stringDictionary={}
for letter in String:
	if letter in stringDictionary:
    	stringDictionary[letter]+=1
    	continue
    stringDictionary[letter]=1
 
queryNo=int(input())
for _ in range(queryNo):
	size=int(input())
    alphabets=list(input().split())
 
	flag=0
	palindromeLength=0
	alphabetset={}
 
	for alphabet in alphabets:
    	if alphabet in alphabetset:
        	continue
        alphabetset[alphabet]=True
 
        value=stringDictionary[alphabet]
    	if value%2==0:
            palindromeLength+=value
        	continue
    	palindromeLength+=value-1
    	flag=1
 
	if flag==1:
        palindromeLength+=1
    print(palindromeLength)
 

```
