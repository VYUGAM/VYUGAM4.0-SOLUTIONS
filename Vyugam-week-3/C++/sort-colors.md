# sort colors - EASY

```c++
#include<bits/stdc++.h>
using namespace std;

void sortColors(vector<int>& nums)
{
       // counting sort approach

       int hash[3] = {0,0,0}; // 0 1 2

       for(int i=0; i<nums.size(); i++)
       {
           hash[nums[i]]++;        
       }

       int cnt = 0;
       for(int i=0; i<3; i++)
       {
           while(hash[i]!=0)
           {
               nums[cnt] = i;
               cnt++;
               hash[i]--;
           }
       }
       for(int i=0;i<nums.size();i++)
       {
           cout<<nums[i]<<" ";
       }

    }

int main()
{
    vector<int> vect;

    int n;

    cin>>n;

    while(n--){

        int x;

        cin>>x;

        vect.push_back(x);

    }

    sortColors(vect);

    return 0;

}
```
