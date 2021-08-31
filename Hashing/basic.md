# Contents:

- Intersection of 2 arrays
- Union of two unsorted arrays
- Pair with given sum

## Intersection of 2 arrays

```
int findIntersection(int a[], int b[], int n, int m){

    unordered_set<int> s(a, a+n);
    int res = 0;
    for(int i = 0; i < m; i++){
        if(s.find(b[i])!=s.end()){
            res++;
            s.erase(b[i]);
        }
    }
    return res;
}

```

## Union of 2 arrays

```
int findUnion(int a[], int b[], int n, int m){

    unordered_set<int> s(a, a+n);
    for(int i = 0; i < m; i++){
        s.insert(b[i]);
    }
    return s.size();
}

```

## Pair with given sum

```
int checkforsumwithpair(int a[], int n, int sum){

    unordered_set<int> s(a, a+n);
    for(int i = 0; i < n; i++){
        if(s.find(sum-a[i])!= s.end()){
            return 1;
        }else{
            s.insert(a[i]);
        }
    }
    return 0;
}

```
