# dsa
2 pointer bruteforce
#include <iostream>
#include<vector>
 // An empty vector of integers
using namespace std;
void twoSum(vector<int> v, int target) {
    for(int i=0; i<v.size();i++) {
        for(int j=i+1;j<v.size();j++) {
            if(v[i]+v[j]==target) {
                cout<<i<<j;
            }
            
        }
    }
}
int main() {
vector<int> v;
v.push_back(3);
v.push_back(2);
v.push_back(4);
std::cout<<"size of vector"<< v.size();
int target =6;
twoSum(v,target);

    return 0;
}
creating hashmaps-
#include <iostream>
#include<unordered_map>
using namespace std;
int main() {
unordered_map<string,int>umap;
umap["shree"]=10;
umap["ankit"]=20;
umap["sid"]=30;
for(auto it:umap)
cout<<it.first<<" "<<it.second<<endl;
    return 0;
}


intersection of array-
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<string, int> umap;
    umap["One"] = 1;
    umap["Two"] = 2;
    umap["Three"] = 3;

    // Using iterator to iterate
    for (auto it = umap.begin(); it != umap.end(); ++it) {
        cout << "Key: " << it->first << ", Value: " << it->second << endl;
    }

    return 0;
}
//reverse array:


#include <iostream>
#include<vector>
using namespace std;
int reverseArr(vector<int>&arr) {
    int start =0;
    int end =arr.size()-1;
    while(start<end) {
       swap(arr[start], arr[end]);
    
    start++;
    end--;
    }
}
int main() {
    // Write C++ code here
    vector<int> arr = {1, 2, 3, 4, 5};
    reverseArr(arr);

    cout << "Reversed Array: ";
    for (int num : arr) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}

alternative

#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

int main() {
vector<int>arr ={1,2,3,4,5};
reverse(arr.begin(), arr.end()); 
    cout << "Reverse is: ";
    
    for (int i : arr) {
        cout << i << " ";
    }
    
    return 0;
}


kadane's algo-
#include<iostream>
using namespace std;
int maxisubarray(int arr[]) {
    int currsum =0;
    int maxsum =0;
    for(int i=0;i<arr.length();i++) {
        currsum =currsum+arr[i];
        if(currsum>maxsum) {
            currsum=maxsum;
        }
        if(currsum<0) {
            currsum =0;
        }
    }
    return maxisubarray();

    return 0;
}

sorting array:-

#include <bits/stdc++.h>
using namespace std;

int main() {
    int arr[] = {11, 9, 45, 21};
    int n = sizeof(arr) / sizeof(arr[0]);
    stable_sort(arr, arr + n, greater<>());
    for (auto i : arr)
        cout << i << " ";
    return 0;
}

