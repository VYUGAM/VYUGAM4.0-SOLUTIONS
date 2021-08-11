# ROW ARITHMETIC - EASY

### TOPIC : MATRICES
```c++

#include <iostream>
using namespace std;

int main() {
    int n,i,j;
    cin>>n;
    int arr[n][n]={0};
    int col_prod[n],col_sum[n]={0};
    for(i=0;i<n;i++)
    {
        for(j=0;j<n;j++)
        {
            cin>>arr[i][j];
        }
    }
    for(i=0;i<n;i++)
        col_prod[i]=1;
    
    for(i=0;i<n;i++)
    {
        for(j=0;j<n;j++)
        {
             col_prod[i]*=arr[i][j];
             col_sum[i]+=arr[i][j];
        }
    }
    
    for(i=0;i<n;i++)
        cout<<col_prod[i]<<" "<<col_sum[i]<<endl;
     return 0;
}
```
