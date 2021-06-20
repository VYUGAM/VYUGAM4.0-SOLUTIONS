# SEQUENCE 2,3,5 - EASY LEVEL PROBLEM - C++

```c++
#include<bits/stdc++.h>
using namespace std;

int main(){
	int t;
	cin>>t;

	while(t--){

		int n;
		cin>>n;
		long long prod=1;

		for(int i=0; i<n; i++){
			int x;
			cin>>x;
			prod = prod * x;
		}
		
		if(prod%10==2 || prod%10==3 || prod%10==5){
			cout<<"YES"<<endl;
		}else{
			cout<<"NO"<<endl;
		}


	}
	return 0;
}
```
