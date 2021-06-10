# Contents:

- Subarray with sum 0
- Subarray with given sum

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
