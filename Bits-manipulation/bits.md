# Contents

- Check if kth bit is set or not
- Count set bits in a number
- Check if number is power of 2 or not
- Odd occuring number
- Two odd occuring numbers in array
- Missing no
- Power set

## Check if kth bit is set or not

```
void setKthBitOrNot(int n, int k){
    if(n&(1<<(k-1))){
        cout<<"Yes";
    }else{
        cout<<"No";
    }
}

```

## Count number of set bits in a number

(Brain Kerningam's Algorithm)

```
int countSetBits(int n){
    int res = 0;
    while(n > 0){
        n = n&(n-1);
        res++;
    }
    return res;
}

```

## Check if power of 2 or not

```
int checkPowerof2(int n){

  return n && (!(n&(n-1)));
}

```

## Odd occuring number

`a[] = {4, 3, 4, 4, 5, 5}`

```
int findOddOccuringElements(int a[], int n){
    int res = 0;
    for(int i = 0; i < n; i++){
        res = res^a[i];
    }
    return res;
}

```

## Missing Number

```
int missingNo(int a[], int n){
    int res = 1, num = a[0];

    for(int i = 2; i <= n+1; i++){
        res = res^i;
    }

    for(int i = 1; i < n; i++){
        num = num^a[i];
    }
    return res^num;
}

```

## Two Odd occuring integers

`a[] = {1, 1, 2, 2, 3, 4}`

```
void twoOddOccuringNums(int a[], int n){

    int XOR = 0, res1 = 0, res2 = 0;
    for(int i = 0; i < n; i++){
        XOR = XOR^a[i];
    }

    int sn = XOR&(~(XOR-1));

    for(int i = 0; i < n; i++){
        if(a[i]&sn!=0){
            res1 = res1^a[i];
        }else{
            res2 = res2^a[i];
        }
    }
    cout<<res1<<" "<<res2;

}
```

## Power Set using bitwise

```
void powerset(string s){

   int n = s.length();

   int powSize = pow(2, n);

   for(int i = 0; i < powSize; i++){
       for(int j = 0; j < n; j++){

           if((i&(1<<j))!=0){
               cout<<s[j];
           }
       }
       cout<<endl;
   }

}


```
