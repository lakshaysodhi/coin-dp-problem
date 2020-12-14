# coin-dp-problem
#include <bits/stdc++.h>
using namespace std;
#define ull unsigned long long
#define ll long long
#define ld long double
#define MOD (ll)(pow(10,9)+7)
#define vec vector<int>
#define pb push_back 


int minno(int n,vec &A,unordered_map<int,int> &H){
           if(n==0) return 0;
           if(H.count(n)!=0)return H[n];
           int ans=INT_MAX;
           for(int i=0;i<A.size();i++){
                      if((n-A[i])>=0)
                      ans=min(minno(n-A[i],A,H)+1,ans);
           }
           return H[n]=ans;
}

int main(){
        
        int n;
        cin>>n;
        vector<int> A(9);
        for(int i=0;i<9;i++)cin>>A[i];
        unordered_map<int,int> H;
        cout<<minno(n,A,H);
        
    return 0;
}
