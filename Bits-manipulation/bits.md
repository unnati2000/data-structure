# Contents

- Check if kth bit is set or not
- Count set bits in a number
- Check if number is power of 2 or not

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
