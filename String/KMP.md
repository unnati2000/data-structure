## KMP algorithm

Before learning KMP algorithm we need to learn LPS ie Longest Proper prefix suffix array

### Proper prefix

Consider "abc" as a string therefore the prefixes of "abc" are:

- ""
- "a"
- "ab"

_Note that the complete string can't be a prefix_

### Suffix

Consider "abc" as a string therefore the suffixes of "abc" are:

- ""
- "c"
- "bc"
- "abc"

### LPS array

LPS array is an array which denotes the proper suffix which also a prefix till the index traversed
Let's consider an example,

Input s: `ababc`
lps[]: `{0, 0, 1, 2, 0}`

Here, the first index of `lps array` will always be zero.
Now, loop through the array

- when we declare i = 1 and loop through it then we compare it with previous characters of the string
- `ab` don't form any proper prefix which also a suffix hence `lps[1] = 0`
- `aba` here LPS is of length 1 ie `a` hence `lps[2] = 1`
- `ababa` here LPS is of length 2 ie `abab` hence `lps[3] = 2`
- `ababc` here there is no LPS hence `lps[4]=0`

### Some examples of LPS

```
    str = aaaa
    output = {0, 1, 2, 3}

    str = abacabad
    output = {0, 0, 1, 0, 1, 2, 3, 0}

```

## Naive method to find LPS of an a string

Takes **O(N3)** time

```
int func(string s, int n){
    for(int i = n-1; i >= 0; i--){
        bool flag = true;
        for(int j = 0; j < i; j++){
            if(s[j] != s[n-i+j])
                flag = false;
        }
        if(flag == true)
            return i;
    }
    return 0;
}

void fillLPS(string s, int *lps){
    for(int i = 0; i < s.length(); i++){
        lps[i] = func(s, i+1);
    }
}
```

## Optimal Solution to find LPS of a string

Let's have a basic gist of this solution will proceed
There are 2 cases for this

- We declare a variable len and `if str[i] == str[len] && len = lps[i-1]` then `lps[i] = len+1 6^ len++`
- `else str[i] != s[len]
  - if `len == 0` then `lps[i] = 0`
  - else, we recursively apply `lps[]` ie `len = lps[len-1]` then again compare `str[i]` with `str[len]`

### code

```
void fillLPS(string s, int *lps){
    int i = 1;
    int len = 0;
    lps[0] = 0;
    while(i < s.length()){
        if(s[i] == s[len]){
            len = len+1;
            lps[i] = len;
            i++;
        }else{
            if(len == 0){
                lps[i] = 0;
                i++;
            }else{
                len = lps[len-1];
            }
        }
    }
}
```

## KMP algorithm

KMP algorithm follows a similar approach as to find LPS of an array

### Code

```
    void KMP(string txt, string pat){

    int n = txt.length();
    int m = pat.length();
    int lps[m];

    fillLPS(pat, lps);

    int i = 0, j = 0;

    while(i < n){
        if(pat[j] == txt[i]){
            i++;
            j++;
        }
        if(j == m){
            cout<<i-j<<" ";
            j = lps[j-1];
        }else if(i < n && (pat[j]!=txt[i])){
            if(j == 0){
                i++;
            }else{
                j = lps[j-1];
            }
        }
    }
}

```
