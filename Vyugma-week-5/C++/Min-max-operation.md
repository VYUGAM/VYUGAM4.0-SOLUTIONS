# MINMAX OPERATION

```c++

#include<bits/stdc++.h>
#define ll long long
using namespace std;

/* The main idea is to use MIN HEAP and MAX HEAP 
   since it is the best way to find min and max elements.

   In C++ it is implemented using Priority queues STL
*/

int main()
{

    int n, q;

    cin>>n>>q;

    priority_queue<ll int> maxh; // MAX HEAP
    priority_queue<ll int, vector<ll int>, greater<ll int>> minh; // MIN HEAP


    // step 1: i) Pushing the elements in MAXHEAP & MIN HEAP DS ii) calculate sum of all elements
    ll int sum=0;

    for(int i=0; i<n; i++){

    	ll int x;
        cin>>x;

        sum+=x;

        maxh.push(x);

        minh.push(x);
   }   

//_______________________________________________________________________________
    // step2 :  Precomputation =>
    //          calculate the all possiblities when we remove in steps
    //          and store result in the array

    ll int t1,t2;

    t1=-1, t2=-1;

    ll int a[n]={0};

    a[0]=sum; //  base sum

    for(int i=1; i<n; i++){

        t1 = maxh.top(); t2=minh.top();

        a[i] = a[i-1]-(t1+t2)+(t1-t2); // calculating sum =>  see how this work in below eg

        maxh.pop(); minh.pop();

        maxh.push(t1-t2); minh.push(t1-t2);
    }
    /*
		sum working:

		3 2 1 5 4
		i=0;   arr[0] = 3+2+1+5+4 = 15
		
		// i) Remove min and max from prev_sum and 
		// ii) add (max-min) to previous sum

		i=1; arr[1] = arr[0] - (1+5) + (5-1)
		     arr[1] = 15 - 6 + 4
		     arr[1] = 13
		.....
    */_____________________________________________________________________________
		//  Step 3: Now using precomputed array,  
		//  we can get any step value in O(1) time complexity
    for(int i=0; i<q; i++){
    	ll int k;
        cin>>k;

        cout<<a[k]<<'\n';

    }
    return 0;   

}

```
