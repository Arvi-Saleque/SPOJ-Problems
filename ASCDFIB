#include <bits/stdc++.h>
using namespace std;

int mp[11000010];
void pre(){
    mp[1] = 0;
    mp[2] = 1;
    for(int i=3;i<=11000005;i++){
        mp[i] = (mp[i-1]+mp[i-2]) % 100000;
    }
}

void Csort(vector<int> &arr){

    int mx = *max_element(arr.begin(),arr.end());
    int mn = *min_element(arr.begin(),arr.end());
    int range = mx - mn + 1;

    vector<int> cnt(range), ans(arr.size());

    for(int i=0;i<arr.size();i++)   cnt[arr[i] - mn]++;

    for(int i=1;i<cnt.size();i++)   cnt[i] += cnt[i-1];

    for(int i=0;i<arr.size();i++){
        int val = arr[i];
        ans[cnt[val - mn] - 1] = val;;
        cnt[val - mn]--;
    }

    arr = ans;

}

int main() {

    int t;
    scanf("%d", &t);

    pre();
    for(int i=1;i<=t;i++){
        int a,b;
        scanf("%d %d",&a,&b);

        printf("Case %d:",i);
        vector<int> vec;
        for(int j=a;j<=a+b;j++){
            vec.push_back(mp[j]);
        }

        Csort(vec);
        int cnt = 0;
        for(auto & x : vec){
             printf(" %d",x);
             cnt++;
             if(cnt==100) break;
        }
        puts("");
    }
}
