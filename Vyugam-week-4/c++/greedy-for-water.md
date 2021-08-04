# Greedy for water

```c++

#include<bits/stdc++.h>
using namespace std;
 
int main(){
 
    int t;
    cin>>t;
 
    while(t--){
 
        int n, capacity;
        cin>>n;
        cin>>capacity;
        
        int bott[n+1];
 
        for(int i=0; i<n; i++){
            cin>>bott[i];
        }
 
        sort(bott, bott+n);
 
        int cnt =0;
 
        for(int i=0; i<n; i++){
 
            if(capacity >= bott[i]){
                cnt++;
                capacity -= bott[i];
            }
 
            if(capacity == 0){
                break;
            }
 
        }    
        cout<<cnt<<endl;
   }
 
    return 0;
}

```
