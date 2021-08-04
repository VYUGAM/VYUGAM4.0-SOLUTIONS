# Passing students

```c++
#include<bits/stdc++.h>
#include<iostream>
using namespace std;

void FindUnion(int m,int n,int arr1[],int arr2[])
{
	int i=0,j=0;
	vector <int> unionPass;
	while (i < m && j < n)
	{
    	if (arr1[i] < arr2[j])
        	unionPass.push_back(arr1[i++]);
 
    	else if (arr2[j] < arr1[i])
        	unionPass.push_back(arr2[j++]);
 
    	else {
        	unionPass.push_back(arr2[j++]);
        	i++;
    	}
	}
	// Print remaining elements of the larger array
	while (i < m)
    	unionPass.push_back(arr1[i++]);
 
	while (j < n)
    	unionPass.push_back(arr2[j++]);
	cout<<unionPass.size()<<endl;;
}

void FindIntersection(int m,int n,int arr1[],int arr2[])
{
	int i = 0, j = 0;
	vector <int> intersectionPass;
	while (i < m && j < n) {
    	if (arr1[i] < arr2[j])
        	i++;
    	else if (arr2[j] < arr1[i])
        	j++;
    	else /* if arr1[i] == arr2[j] */
    	{
        	intersectionPass.push_back(arr2[j]);
        	i++;
        	j++;
    	}
	}
	cout<<intersectionPass.size();
}

int main()
{
	int s,m,i;
	cin>>m;
	int MathPass[m];
	for(i=0;i<m;i++)
    	cin>>MathPass[i];
	cin>>s;
	int SciencePass[s];
	for(i=0;i<s;i++)
    	cin>>SciencePass[i];
	//To find the students who passed in either Math or Science
	FindUnion(m,s,MathPass,SciencePass);
	//To find the students who passed in both Math or Science
	FindIntersection(m,s,MathPass,SciencePass);
	return 0;
}

```
