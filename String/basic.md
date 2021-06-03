## A string is a subseq of other or not

```
    int n = s1.length();
    int m = s2.length();
    int i = 0, j = 0;

    while(i<n && j < m){

        if(s1[i] == s2[j]){
            j++;
            i++;
        }
        i++;
    }
    if(j == m){
        return 1;
    }
```
