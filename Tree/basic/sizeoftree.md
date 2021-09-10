## Size Of Binary Tree

```
int sizeOfTree(Node *root){
    if(root!=NULL){
    int l = sizeOfTree(root->left);
    int r = sizeOfTree(root->right);
    return 1+l+r;    
    }
    
}
    
```