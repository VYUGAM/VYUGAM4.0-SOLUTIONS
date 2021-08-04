# ROTATING STRING PAIRS

```c++
#include <iostream>
using namespace std;
bool checkRotation(string str1, string str2)
{
if(str1.length()!=str2.length())
    	return false;
string temp=str1+str1;
if(temp.find(str2)!= string::npos)
    	return true;
else
    	return false;
}
int main()
{
int N,n,i=0,j,count=0;
string str1,str2;
bool check;
cin>>N;
while(i<N)
{
    	cin>>str1>>str2;
    	check=checkRotation(str1,str2);
    	if(check==true)
        	count++;
    	i++;
}
cout<<count;
return 0;
}

```
