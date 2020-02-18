# K-largestElement

#include<queue>

using namespace std;
vector<int> kLargest(int input[], int n, int k){
    
    priority_queue<int,vector<int>,greater<int>> p;
    
    
  for(int i=0;i<k;i++){
      p.push(input[i]);
  }
    
    for(int i=k;i<n;i++){
        if(p.top()<input[i]){
            p.pop();
            p.push(input[i]);
        }
    }
    
    vector<int> v;
    while(!p.empty()){
        v.push_back(p.top());
        p.pop();
    }
    
    return v;
    
}
