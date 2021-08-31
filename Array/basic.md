# Contents

- remove duplicates from an array
- move all negative elements to one side
- leaders in an array
- Kth max and kth min

## Remove Duplicates from an Array

```
 int removeDuplicates(vector<int>& nums) {
        
        if(nums.size() > 0){
           int res = 1;
            for(int i = 1; i < nums.size(); i++){
                if(nums[i]!=nums[res-1]){
                    nums[res] = nums[i];
                    res++;
                }
            }
            return res; 
        }else{
            return 0;
        }
}

```

## Remove duplicates

```
    for(int i = 0; i < n; i++){

        if(a[abs(a[i])] > 0){
            a[abs(a[i])] = -a[abs(a[i])];
        }else{
            cout<<abs(a[i])<<endl;
        }
    }

```

## Move all negative elements to one side

```
    void func(int a[], int n){

        int i = 0, j = n-1;

        for(int i = 0; i < n; i++){

            if(a[i]< 0){
                if(i!=j){
                    swap(a[i], a[j]);
                    j++;
                }
            }
        }
    }

```

## Leaders in an array

Nothing has to be greater than the element to the right

I/p: 5 6 1 2 4
o/p: 6 6 4 4 4

```
    void leaders(int a[], int n){

        int t = a[n-1];
        for(int i = n-2; i >= 0; i--){

            if(t < a[i]){
                t = a[i];
                cout<<a[i]<<" ";
            }

        }
    }

```

## Kth max and Kth min

- Here, we use priority_queue
- priority_queue is intialised is filled with first k values and sorted in the order of max heap

```
    void function(int a[], int n, int k){

        <!-- filled queue with first k values in reverse order -->
        priority_queue<int, greater<int>> q(a, a+k);

        for(int i = k; i < n; i++){

            if(a[i] > q.top()){
                q.pop();
                q.push(a[i]);
            }

        }

        while(!q.empty()){
            cout<<q.top();
            cout<<q.pop();
        }
    }

```
