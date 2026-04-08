# DSC Club
#These Are the DSC Club - Competitive Programming Questions


#include <bits/stdc++.h>
using namespace std;

Ques 2 : Lets Assusme that First is Presend in the Hashmap and we try to serach for the previous element in the Hashmap , if it isnt present we just calcualte the Max;
    TC :- O(n) (optimal Soluution);
int main(){
    vector<int>vec = {100, 4, 200, 1, 3, 2};
    unordered_set<int>m;
    int count = 0;
    for(auto i : vec){
        m.insert(i);
    }
    int Max= 0;
    for(auto i : m){
        if(m.find(i - 1) != m.end()){
            int count = 0;
            int j = 0;
            while(m.find(i - j) != m.end()){
                count++;
                j++;
            }
            Max = max(count , Max);
        }
    }
    cout << Max;
}


Ques 3 :- This Qs Uses the Prefix-sum pattern and uses the Hashmap to store the Prefix-sums, we need to search Prefix - target, if its present the Subarray sum is Equal to target 
int main(){
    vector<int>vec = {1,1,1};
    vector<int>ans;
    int pre = 0;
    int tar = 2;
    int count = 0;
    unordered_map<int,int>m;
    for(int i=0;i<vec.size();i++){
        pre += vec[i];
        ans.push_back(pre);
        if(pre == tar){
            count++;
        }
    }
    for(auto i : ans){
        if(m.find(i-tar) != m.end()) count+=m[i-tar];
        m[i]++;
    }
    cout << count;
}
