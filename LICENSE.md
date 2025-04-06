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


// priority_queue<ll>q1;
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




void solve(){
    ll n,num1=0,sum=0,flag1=0,num2=0,maxx=0,num3=0;
    cin>>n;
    for(int i=1;i<=n;i++){
        cin>>a[i];
        b[i]=a[i];
        mp[a[i]]++;
        mp1[a[i]]=i;
    }
    for(int i=1;i<=n;i++){
        if(a[i]==0){
            num2=i-1;
            break;
        }
    }
    ll num=n-mp1[1];
    if(mp[0]-1-num2>=mp[1]-1-num){
        for(int i=1;i<=n;i++){
            if(a[i]==0){
                if(flag1==0){
                 a[i]=1;
                 flag1=1;
                }
                else{
                sum+=num1;
                }
             }
            if(a[i]==1){
                num1++;
            }
            if(b[i]==0){
                maxx+=num3;
            }
            else{
                num3++;
            }
        }
    }
    else{
        a[mp1[1]]=0;
        for(int i=1;i<=n;i++){
            if(a[i]==0){
                sum+=num1;
             }
            if(a[i]==1){
                num1++;
            }
        
        if(b[i]==0){
            maxx+=num3;
        }
        else{
            num3++;
        }
    }
    }
    cout<<max(maxx,sum)<<endl;
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
