#include <iostream>
#include <vector>
using namespace std;
int listending(vector<int>&a,int idx,vector<int>memo){
if(idx==0)
 {return 1;}
 int mx=1;
 if(memo[idx]!=-1)
 return memo[idx];
 for(int pre=0;pre<idx;pre++)
 if(a[pre]<a[idx])
 
    mx=max(mx,listending(a,pre,memo)+1);
   memo[idx]=mx;
     return memo[idx];
}
   int list(vector<int>&a) {
  
     int n=a.size();
     vector<int>memo(n,-1);
    int res=1;
    for(int i=1;i<n;i++)
    res= max (res, listending(a,i,memo));
    return res;
}
int main()
{
 vector<int>a={10,0,55,0,90};
 cout<<list(a);
 return 0;

}
