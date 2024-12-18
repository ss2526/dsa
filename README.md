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
umap["srk"]=30;
for(auto it:umap)
cout<<it.first<<" "<<it.second<<endl;
    return 0;
}
#include<iostream>
#include<unordered_map>
#include<vector>
using namespace std;

vector<int> intersectionOfArrays(int arr1[], int n1, int arr2[], int n2) {
    unordered_map<int, int> map;
    vector<int> intersection;
    
    // Step 1: Store frequency of elements from the first array in the hashmap
    for (int i = 0; i < n1; i++) {
        map[arr1[i]]++;
    }

    // Step 2: Traverse the second array and check for intersection
    for (int i = 0; i < n2; i++) {
        if (map[arr2[i]] > 0) {  // Check if element exists in the hashmap
            intersection.push_back(arr2[i]);
            map[arr2[i]] = 0;  // Mark the element as "used" by setting its count to 0
        }
    }

    return intersection;
}

int main() {
    int arr1[] = {1, 2, 2, 1, 4};
    int arr2[] = {2, 2, 4, 5, 1};

    int n1 = sizeof(arr1) / sizeof(arr1[0]);
    int n2 = sizeof(arr2) / sizeof(arr2[0]);

    vector<int> result = intersectionOfArrays(arr1, n1, arr2, n2);

    cout << "Intersection of arrays: ";
    for (int num : result) {
        cout << num << " ";
    }
    cout << endl;

    return 0;
}


unique elemnents:-
#include<iostream>
#include<unordered_set>  // For unordered_set (hashset)
using namespace std;

int countDistinctElements(int arr[], int n) {
    unordered_set<int> distinctElements;
    
    // Insert each element into the unordered_set
    for (int i = 0; i < n; i++) {
        distinctElements.insert(arr[i]);
    }
    
    // The number of distinct elements is the size of the set
    return distinctElements.size();
}

int main() {
    int arr[] = {1, 2, 2, 3, 4, 5, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    
    int result = countDistinctElements(arr, n);
    cout << "Number of distinct elements: " << result << endl;
    
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


union:-
#include<iostream>
#include<unordered_set>  // For unordered_set (hashset)
#include<vector>         // For vector to store the result
using namespace std;

vector<int> unionOfArrays(int arr1[], int n1, int arr2[], int n2) {
    unordered_set<int> unionSet;
    
    // Insert elements of arr1 into the set
    for (int i = 0; i < n1; i++) {
        unionSet.insert(arr1[i]);
    }

    // Insert elements of arr2 into the set
    for (int i = 0; i < n2; i++) {
        unionSet.insert(arr2[i]);
    }

    // Convert the unordered_set to a vector for returning the result
    vector<int> result(unionSet.begin(), unionSet.end());
    return result;
}

int main() {
    int arr1[] = {1, 2, 2, 3, 4};
    int arr2[] = {3, 4, 5, 6};
    
    int n1 = sizeof(arr1) / sizeof(arr1[0]);
    int n2 = sizeof(arr2) / sizeof(arr2[0]);
    
    vector<int> result = unionOfArrays(arr1, n1, arr2, n2);
    
    cout << "Union of arrays: ";
    for (int num : result) {
        cout << num << " ";
    }
    cout << endl;
    
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
maxarray:-
#include<iostream>
using namespace std;
int maxarray(int n, int arr[]) {
    for(int i=0;i<n-1;i++) {
        if (arr[i]<arr[i+1]) {
            cout<< "sorted";
        }
      else {
        cout<<"not sorted"; 
     }  
   }
}
int main() {
    int arr[]= {1,4,5,7,2,6,4};
    int n= sizeof(arr)/sizeof(arr[0]);
    cout<<"size of array"<<n<<endl;
    maxarray(arr[],n);
   return 0;
   
}
Purpose
HashMap: A HashMap is a collection that stores key-value pairs, where each key is associated with exactly one value. It allows for fast retrieval, insertion, and deletion of elements based on the key.
HashSet: A HashSet is a collection that only stores unique elements. It does not maintain any association between keys and values. It is used to store a set of unique elements without duplicates.
2. Data Structure
HashMap: Internally, it stores entries as key-value pairs (<key, value>). The key is unique, but the value can be duplicated.
HashSet: It only stores the key (or element) itself. The HashSet internally uses a HashMap to store elements (keys), but only the keys are used, and the values are typically ignored.
