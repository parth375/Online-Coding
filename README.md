# Maximize-Multiples
#include <iostream>
#include<vector>
using namespace std;

int main()
{
    vector<int>v;
 int n,m,k;
cin>>n>>m>>k;
int arr[n];
for(int i=0;i<n;i++){
    cin>>arr[i];
}
for(int i=0;i<n;i++){
    if(arr[i]%m!=0){
        v.push_back(arr[i]);
    }
}
int r=n-v.size();

int cnt=0;
int i=0;
while(k>0 && i<v.size()){
    int b=m-1;
    if((v[i]+b)%m==0){
        cnt++;
        k=k-b;
        i++;
    }
    else if((v[i]+1)%m==0){
        cnt++;
        k=k-1;
        i++;
    }
    else{
        i++;
    }
}
cout<<cnt+r<<endl;


    return 0;
}
