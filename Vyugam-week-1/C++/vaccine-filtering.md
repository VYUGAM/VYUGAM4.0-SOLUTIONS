# VACCINE FILTERING -MEDIUM C++
```c++

#include <bits/stdc++.h>
using namespace std;

int main() {

	int m,n;
	cin>>m>>n;

	long long arr[m+1][n+1]={};

	// Storing values in 2d array
	for(int i=1; i<=m; i++){
		for(int j=1; j<=n; j++){
			int x;
			cin>>x;

			if(x%2!=0){ //  odd number  so incorrect vaccine
			arr[i][j] = 1;
			}else{  // even number correct vaccine
				arr[i][j] = 0;
			}
		}
	}

	// Forming pre-computation matrix

	// row sum
	for(int i=1; i<=m; i++){
		for(int j=1; j<=n; j++){
			
			if(j>1){
				arr[i][j] = arr[i][j] + arr[i][j-1];
			}
		}
	}
	// column sum
	for(int i=1; i<=m; i++){
		for(int j=1; j<=n; j++){
			
			if(i>1){
				arr[i][j] = arr[i][j] + arr[i-1][j];
			}
		}
	}

	// for(int i=1; i<=m; i++){
	// 	for(int j=1; j<=n; j++){
	// 		cout<<arr[i][j]<<" ";
	// 	}
	// 	cout<<endl;
	// }

	//Calculate the query sum

	int q;
	cin>>q;

	while(q--){

		int a,b,c,d;

		cin>>a>>b>>c>>d;
		long long sum = arr[c][d] - arr[a-1][d] - arr[c][b-1] +arr[a-1][b-1];
		cout<<sum<<endl;

	}
	

return 0;

}



```
