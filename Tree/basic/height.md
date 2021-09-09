## Height of Binary Tree

**Time Complexity O(h)**

```
int max(int a, int b){
    return a > b ? a : b;
}

int height(Node *root){
    
    if(root==NULL){
        return 0;
    }else{
        int l = height(root->left);
        int r = height(root->right);
        return max(l,r)+1;
    }
    
}



```