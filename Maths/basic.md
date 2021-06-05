# Contents

- armstrong number
- number of digits in a number
- palindrome
- reverse a num
- closest number

## Armstrong number

Armstrong number is a number whose sum of individual digit raised to its power is equal to its number.
eg 153 = `1*1*1 + 5*5*5 + 3*3*3 = 153`

### code

```
   int n;
   cin>>n;
   int len = 0;
   int n1 = n;
   while(n1 > 0){
       len++;
       n1 = n1/10;
   }

   n1 = n;
   int sum = 0;

   while(n1 > 0){
       int r = n1%10;
       sum = sum + pow(r, len);
       n1 = n1/10;
   }

   if(sum == n){
       cout<<"Yes"<<endl;
   }else{
       cout<<"No"<<endl;
   }
```

## Number of digits in a number

### Recursive solution

```
int dig(int n){

    if(n == 0){
        return 0;
    }else{
        return 1+dig(n/10);
    }
}
```

### Log N solution

```
int dig(int n){
   return floor(log10(n)+1);
}
```

## Reverse digits

```
int reverse(int n){

    int rev = 0;

    while(n > 0){
        rev = rev*10 + n%10;
        n = n/10;
    }
    return rev;
}
```

## Closest number

```
    int q = n / m;
    int n1 = m * q;
    int n2 = (n * m) > 0 ? (m * (q + 1)) : (m * (q - 1));

    (abs(n - n1) < abs(n - n2)) ? cout<<n1<<" "<<n2;
```
