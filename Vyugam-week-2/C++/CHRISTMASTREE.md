# CHRISTMAS TREE

```c++
#include<bits/stdc++.h>
 
using namespace std;

//  lets print the tree
  
int main(){
	
	int t;
	cin>>t;
 
	while(t--){
 
		int h;
		cin>>h;
 
		long long a[h][h] = {};
 
		a[0][0] = 1;
 
		for(int i=0; i<h; i++){
 
			for(int j=0; j<h; j++){
				//a[i][j] =0;
				if(i>=j){
 
					if(i==j || j==0){
						a[i][j] = 1;
					}
					else{
 
						a[i][j] = a[i-1][j-1] + a[i-1][j];
 
					}
 
 
				}
 
			}
		}
			// lets print the tree
 
			for(int i=0; i<h; i++){
 
					for(int j=0; j<h; j++){
 
						if(i>=j){
						cout<<a[i][j]<<" ";
						}
					}
					cout<<endl;
			}
 
	}
	
	return 0;
}
 

```
