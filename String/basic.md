- check for subsequence

## A string is a subseq of other or not

```
   string s1, s2;
   cin>>s1;
   cin>>s2;
   int i = 0, j = 0;
   while(i < s1.size() && j < s2.size()){
       
       if(s1[i] == s2[j]){
           
           i++;
           j++;
       }
       i++;
       
   }
   j == s2.size() ? cout<<"Yes" :cout<<"No"<<endl;
```

## Anagram of two strings
```
  string s1, s2;
   cin>>s1;
   cin>>s2;
    int count[CHAR] = {0};
    
    if(s1.size()!=s2.size()){
        cout<<"N0"<<endl;
    }else{
         for(int i = 0; i < s1.size(); i++){
            count[s1[i]]++;
            count[s2[i]]--;
        }     
        
        for(int i = 0; i < CHAR; i++){
            if(count[i] != 48){
                cout<<"No"<<endl;
            }
        }
    }


```

## Left most repeating character

```
    const int CHAR = 265;
   int count[CHAR] = {0};
        
    for(int i = 0; i < s1.size(); i++){
         count[s1[i]]++;
     }     
            
    for(int i = 0; i < CHAR; i++){
        if(count[i] > 1){
            cout<<i-96<<endl;
            break;
        }
    }

```

```
    int count[CHAR] = {-1};
    int ind;
    string s;
    cin>>s;
    int res = INT_MAX;
    
    for(int i = 0; i < s.size(); i++){
        
        ind = s[i];
        
        if(count[ind] == -1){
            count[s[i]] = i;
        }else{
            res = res > ind ? ind: res;
        }
        
    }
   
    cout<<res<<endl;

```
