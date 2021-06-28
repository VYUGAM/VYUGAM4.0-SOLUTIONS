# RIDDLE GAME-EASY

```c++
#include<bits/stdc++.h>
#define ll long long int
 
using namespace std;
 
int main(){
	
	// Binary to decimal - GPL
	
	int t;
	cin>>t;
 
	while(t--){
 
		int n;
		cin>>n;
		string s;
		cin>>s;
 
		long long result = 0;
		long long pow2 = 1; // 2^0
 
		for(int i=s.size()-1; i>=0; i--){
 
			int bin_digit = s[i] - '0';
 
			result = result + (bin_digit*pow2);
			pow2 = pow2*2;
 
		}
		cout<<result<<endl;
 
	}
 
	return 0;
}

```
