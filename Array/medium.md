# Contents

- largest sum subarray
- majority element

## Lagest sum subarray problem

```
    int maxSubarray(int a[], int n){

        int prev = INT_MIN, curr = 0;

        for(int i = 0; i < n; i++){

            curr = curr+a[i];
            if(curr > prev){
                prev = curr;
            }
            if(curr<0){
                curr = 0;
            }
        }
        return curr;
    }

```

## Majority element

- This method follows 2 approaches
- First, finding the number
- Second checking if its majority or not

### Find num

```
    int majElement(int a[], int n){

        int maj = 0, count = 1;

        for(int i = 1; i < n; i++){

            if(a[i] == a[maj]){
                count++;
            }else{
                count--;
            }

            if(count == 0){
                maj = i;
                count = 1;
            }
        }
        return a[maj];
    }

```

### Check if it is majority or not

```
    bool isMaj(int a[], int n, int maj){

        int count = 0;
        for(int i = 0; i < n; i++){
            if(a[i] == maj){
                count++;
            }
        }

        if(count >= n/2){
            return true;
        }else{
            return false;
        }
    }
```
