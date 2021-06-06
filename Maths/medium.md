# Contents

- trailing zeros
- GCD
- LCM
- power
  - recursive
  - iterative

## Trailing zeros

```
    int int countTrailingZeros(int n){
	int res = 0;
	for(int i=5; i<=n; i=i*5){
		res = res + (n / i);
	}
	return res;
}
```

## GCD (Euclids algorithm)

_Always pass bigger number first_

```
int GCD(int a, int b){
    if(b == 0){
        return a;
    }else{
        return (b, a%b);
    }
}

```

## LCM

```
int LCM(int a, int b){

   int max = a>b ? a:b;
   while(true){
       if(max%a == 0 && max%b == 0){
           return max;
       }
       max++;
   }
   return 0;
}

```

## Compute power efficient approach

```
int power(int a, int b){

    int temp;
    if(b == 0){
        return 1;
    }
    temp = power(a, b/2);
    if(b%2 == 0){
        return temp*temp;
    }else{
        return temp*a*temp;
    }
}

```
