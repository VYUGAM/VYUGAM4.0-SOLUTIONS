# A XOR Operation -  HARD

```c++
#include<bits/stdc++.h>
using namespace std;
#define int long long int
int32_t main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        vector<int> nums(n);
        for(int i=0;i<n;i++)
        {
            cin>>nums[i];
        }
        unordered_map<int,int> mp;
        int x=0LL;
        for (int i : nums)
        {    
            x^=i;
            mp[i]=1;
        }
        int flag=0;
        for(int i : nums)
        {
            int temp=i^x;
            if(mp[temp]!=1)
            {
                flag=1;
            }
        }
        if(flag){
            cout<<-1<<'\n';
        }
        else{
            cout<<x<<'\n';
        }
    }
}
```
