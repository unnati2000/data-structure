## Nodes at Kth distance

```

void nodesatkth(Node *root, int k){
    if(root == NULL){
        return;
    }else if(k == 0){
        cout<<root->data<<" ";
    }else{
        nodesatkth(root->left, k-1);
        nodesatkth(root->right, k-1);
    }
}

```