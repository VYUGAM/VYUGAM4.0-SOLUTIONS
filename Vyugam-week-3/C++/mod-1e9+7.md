# Can you win the challenge? - EASY


```c++
# include<bits/stdc++.h>
# define MOD 1000000007
using namespace std;
 
int main(){
 
    int n;
    cin>>n;
 
    // Modulo 10^9 + 7
    long long fact = 1;
 
    for(int i=2; i<=n ; i++){
        fact = (fact%MOD * i%MOD )%MOD ;
    }
 
    cout<<fact;
 
    return 0;
 
}


```
