# Coins-change - HARD

```c++
# include<bits/stdc++.h>
using namespace std;

int memo[102][102];

int coinschange(int supply[], int s, int N){

	if(s==0 && N>0){
		return 0;
	}
	if(N==0){
		return 1;
	}
	// memo
	if(memo[s][N]!=-1){
		return memo[s][N];
	}

	if(supply[s-1] <= N){
		// since infinite supply while picking we are not decreasing s
		return memo[s][N] = coinschange(supply, s, N-supply[s-1]) + coinschange(supply, s-1, N);
	}else{
		// not pick
		return memo[s][N] = coinschange(supply, s-1, N);
	}

}

int main(){

	int N, s;

	cin>>N>>s;

	int supply[s+1];

	for(int i=0; i<s;i++){
		cin>>supply[i];
	}

	memset(memo, -1, sizeof(memo));

	cout<<coinschange(supply, s, N);

	return 0;
}


```
