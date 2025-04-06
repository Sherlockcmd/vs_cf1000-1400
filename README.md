//题目地址https://codeforces.com/problemset/problem/1905/B
本题难度1100（贪心，树形结构）
#include<bits/stdc++.h>
#include<stdlib.h>
#include<string>
#include<algorithm>
#include<map>
#include<stack>
#include<queue>
#include<deque>
#include<numeric>
#include<vector>
#include<unordered_map>
#include<climits> 
#define ll long long
#define ull unsigned long long
#define endl "\n" 
#define fi first
#define se second
#define vi vector
#define pb push_back

using namespace std;
const ll N=2e6+5,M=1e7+5;
const int mod=1e9+7;
ll a[N]={0},b[N]={0},c[N]={0},d[N]={0};


//priority_queue<ll>q;//大
//priority_queue<int,vector<int>,greater<int> >q;//小

map<ll,ll>mp; map<ll,ll>mp1;map<int,vector<int>>mp2;
//----------------------------------------------------------------------
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
    }//最大公约数
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
    }//最小公倍数
//----------------------------------------------------------------------
//-----------------------------并查集-----------------------------------
// ll f[N];

// int find(int i){
//    if(i!=f[i]){
//    	f[i]=find(f[i]);
//    }
//    return f[i];
// }
// bool sameset(int x,int y){
//     return find(x)==find(y);
// }
// void sumset(int x,int y){
//  int fx=find(x);     
//  int fy=find(y);
//   f[fx]=fy;
// }
//----------------------------------------------------------------------

//-------------------------------bfs------------------------------------
bool vis[200][200];
int move1[]={-1,0,1,0,-1};//上右下左
//----------------------------------------------------------------------

//----------------------------------------------------------------------

struct STR{
    ll x=0,id;
}str[N];

// struct cmp
// {
//     bool operator()(STR a,STR b){
//         if(a.hp==b.hp){
//             if(a.k==b.k){
//                 return a.id>b.id;
//             }
//             else return a.k>b.k;
//         }
//         return a.hp>b.hp;
//     }
// };
bool cmp(STR a,STR b){
    return a.x>b.x;
}



void solve(){
    ll n;
    cin>>n;
    for(int i=1;i<n;i++){
        ll x,y;
        cin>>x>>y;
        mp[x]++;
        mp[y]++;
    }
    ll num=0;
    for(auto it:mp){
       if(it.se==1){
        num++;
       }
    }
    cout<<num-(num/2)<<endl;
     return;
}



int main(){ 
	
  std::ios::sync_with_stdio(0);
  std::cin.tie(0);cout.tie(0);

	
    int T=1;
    cin >> T;
    while (T--) {
	solve();
    mp.clear();
    mp1.clear();
    mp2.clear();
    }
    return 0;
}
