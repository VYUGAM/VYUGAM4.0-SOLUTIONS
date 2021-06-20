# UPPER WALL - EASY C++
```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
	
	string s;
	cin>>s;

	while(s.size()!=0){

		for(int i=0; s[i]!='\0'; i++){
			cout<<char(s[i]-'a'+'A');
		}
		cout<<endl;

		s="";
		cin>>s;
	}
}

```
