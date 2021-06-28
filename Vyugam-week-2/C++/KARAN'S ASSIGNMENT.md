# KARANS ASSIGNMENT - EASY

```c++
#include<iostream>
using namespace std;
int main()
{
        int a, b, x, y, temp, hcf, lcm;
        cin>>x>>y;
        a=x;
        b=y;
        while(b!=0)
        {
                temp=b;
                b=a%b;
                a=temp;
        }
        hcf=a;
        lcm=(x*y)/hcf;
        cout<<hcf<<"\n";
        cout<<lcm<<"\n";
        return 0;
}


```
