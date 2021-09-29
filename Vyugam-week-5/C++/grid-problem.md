# GRID PROBLEM

### Time complexity : O(N^2)
### Space complexity : O(N^2)

```c++
#include<bits/stdc++.h>
using namespace std;
 
bool check(char a,char b,char c,char d)
{
  if(a=='s' && b=='a' && c=='b' && d=='a')
    return true;
  return false;
}
 
int main()
{
 	// Character grid
  char jad[105][105]; //since given max of N & M is 100
  int n,m,ans=0;
  cin>>n>>m;
 
 //Get the input for grid
  for(int i=1;i<=n;i++)
    for(int j=1;j<=m;j++)
      cin>>jad[i][j];
 
	// BRUTE FORCE APPROACH
 
	// i) check diagonal (D1)
	/*	s
			a
				b
					a
	*/
  for(int i=4;i<=n;i++)
    for(int j=1;j<=m-3;j++)
      if(check(jad[i][j],jad[i-1][j+1],jad[i-2][j+2],jad[i-3][j+3]))
	ans++;
 
 
	// ii) check Horizontally 
	// s a b a
  for(int i=1;i<=n-3;i++)
    for(int j=1;j<=m-3;j++)
      if(check(jad[i][j],jad[i+1][j+1],jad[i+2][j+2],jad[i+3][j+3]))
	ans++;
 
	// iii) check Vertically
	/*	s
		a
		b
		a
	*/
  for(int i=1;i<=n;i++)
    for(int j=1;j<=m-3;j++)
      if(check(jad[i][j],jad[i][j+1],jad[i][j+2],jad[i][j+3]))
	ans++;
 
 
	// iv) check Diagonally (bottom to top)
	/*
					a
				b
			a
		s
	*/
 
  for(int i=1;i<=n-3;i++)
    for(int j=1;j<=m;j++)
      if(check(jad[i][j],jad[i+1][j],jad[i+2][j],jad[i+3][j]))
	ans++;
 
  
  cout<<ans<<endl;
 
  return 0;
}




```
