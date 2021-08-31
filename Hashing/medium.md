# Contents:

- Subarray with sum 0
- Subarray with given sum
* Longest subarray with given sum

## Subarray with sum 0

```
int checkforsumwith0(int a[], int n){

    unordered_set<int> s;
    int preSum = 0;
    for(int i = 0; i < n; i++){
        preSum = preSum + a[i];

        if(s.find(preSum)!= s.end()){
            return 1;
        }
        if(preSum == 0){
            return 1;
        }
        s.insert(preSum);
    }
    return 0;
}


```

## Subarray with given sum

```
int checkforgivensum(int a[], int n, int sum){

    unordered_set<int> s;
    int preSum = 0;
    for(int i = 0; i < n; i++){
        preSum = preSum + a[i];

        if(s.find(preSum)!= s.end()){
            return i+1;
        }
        if(preSum == sum){
            return 1;
        }
        s.insert(preSum);
    }
    return 0;
}

```

## Longest subarray with given sum
```
int longestSubarray(int a[], int n, int sum){
    
    unordered_map <int, int> mp;
    int pre_sum = 0, res = 0;
    for(int i = 0; i < n;i++){
        
        pre_sum = pre_sum+a[i];
        if(pre_sum == sum){
            res = i+1;
        }
        if(mp.find(pre_sum) == mp.end()){
            mp[a[i]] = i;
        }
        if(mp.find(pre_sum-sum)!= mp.end()){
            res = max(res, i-mp[pre_sum-sum]);
        }
    }
    return res;
}
```
