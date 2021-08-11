# MOST BOUGHT AGE GROUP - EASY

### TOPIC : STRUCTURES

```c++
#include <iostream>
#include<bits/stdc++.h>
using namespace std;

struct customer
{
    int id;
    string name;
    int age;
};

int main()
{
    int n,i;
    cin>>n; //Get no of customers
    customer c[n]; //Declare structure variable
    int age_grp[4]={0};
    for(i=0;i<n;i++)
    {
        cin>>c[i].id>>c[i].name>>c[i].age;
        
        if(c[i].age<=14)  //Children
            age_grp[0]++;
        else if(c[i].age<=24)  //Youth
            age_grp[1]++;
        else if(c[i].age<=64)   //Adults
             age_grp[2]++;
        else    //>65 are Seniors
            age_grp[3]++;
    }

    int max=0;
    for(i=0;i<4;i++)
    {
        if(max<age_grp[i])
            max=i;
    }
    
    if(max==0)
        cout<<"Children";
    else if(max==1)
        cout<<"Youth";
    else if(max==2)
        cout<<"Adults";
    else
        cout<<"Seniors";
    return 0;
}
```
