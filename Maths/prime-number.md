# Contents

- If number is prime or not
- prime factors
  - naive
  - more efficient
  - most efficient
- divisor of a number

## If a number is prime or not

```
    bool isPrime(int n){

        if(n == 1)
            return false;
        if(n == 2 || n == 3)
            return true;
        for(int i = 5; i*i <= n; i = i+6){
            if(n%i == 0 || n%(i+2) == 0){
                return false;
            }
        }
        return true;
    }

```

## Prime factors

### Naive Method
