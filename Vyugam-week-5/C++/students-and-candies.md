# STUDENTS AND CANDIES

```c++

#include<bits/stdc++.h>
using namespace std;
/*
	Main idea is to use Binary search tree to access elements in logn time
	Here , we use set c++ STL container which is internally a binary search tree implemented.
*/
int main(){

	int t;
	cin>>t;

	while(t--){

		int n,m;
		cin>>n>>m;

		int num = n+m;
	
               set<long long int> A;
		// ith got Ai candies


		// Step1: Insert first n students
		for(int i = 0; i<n; i++){
			
			long long int x;
			cin>>x;

			A.insert(x);
		}

		int size;

		//Step 2:  Try to insert next m students

		for(int i=0; i<m; i++){
			 long long int x;
			 cin>>x;

			size = A.size(); // before insertion

			A.insert(x);

// Main logic: Array size remains same if that elemts already exists(duplicate)
// Since in Binary search tree only unique values are stored (set STL implementation)

	     if(size == A.size()){ // check size before and after insertion
				cout<<"YES";
		}else{
				cout<<"NO";
		}

			 cout<<endl;
		}



	}



	return 0;


```
