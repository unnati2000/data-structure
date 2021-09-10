## Get maximum number in tree

```
int getMax(Node *root){
    
    if(root == NULL){
        return 0;
    }else{
        return max(root->data, max(getMax(root->left), getMax(root->right)));
    }   
}

```