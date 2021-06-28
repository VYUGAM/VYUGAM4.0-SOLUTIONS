# HELP JOE - MEDIUM

```c++

#include<bits/stdc++.h>
using namespace std;
int main(){
   string str;
   cin>>str;
 
    int hash[26]={0};
   // initialize to zero
 
   for(int i=0; str[i]!='\0'; i++){
       hash[str[i]-'a']++ ;
   }
 
   long long q;
   cin>>q;
 
   while(q--){
 
        int n;
        cin>>n;
        long long pal_size=0;
        vector<int> unique(27,0);
 
        // Step1: Getting unique characters
        for(int i=0; i<n;i++){
 
            char c;
            cin>>c;
 
            unique[c-'a'] = 1;
        }
 
        // Step2: Finding palindrome size
        bool odd_present = false;
 
        for(int i=0; i<26; i++){
            
            if(unique[i]==0){ continue;}
            int char_ct = hash[i];
 
            if(hash[i]%2 ==0){
                pal_size += char_ct;
            }else{
                pal_size += (char_ct-1);// even part of odd numb
                odd_present = true;
            }
        }
 
        if(odd_present){ pal_size++; }
 
        cout<<pal_size<<endl;
 
 
 
   }
 
 
   return 0;
}
 


```
