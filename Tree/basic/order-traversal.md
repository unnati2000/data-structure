
## Basic Code
```
struct Node  
{ 
  int data; 
  struct Node *left; 
  struct Node *right; 
  Node(int k){
      data=k;
      left=right=NULL;
  }
};


int main() {
    // Write C++ code here
    
    Node *root = new Node(10);
    root->left= new Node(20);
    root->right= new Node(30);
    root->left->right= new Node(40);
    root->right->left= new Node(50);
    
    inorder(root);
    

    return 0;
}


```

## Inorder Traversal

**Time complexity: O(h)**

```
void inorder(Node *root){
    
    if(root!=NULL){
        inorder(root->left);
        cout<<root->data<<" ";
        inorder(root->right);     
    }
   
}

```

## Pre Traversal

**Time complexity: O(h)**

```

void preOrder(Node *root){
    
    if(root!=NULL){
       
        cout<<root->data<<" ";
         preOrder(root->left);
        preOrder(root->right);     
    }
   
}

```

## Post Order

**Time Complexity O(N)**
```
void postOrder(Node *root){
    
    if(root!=NULL){
        postOrder(root->left);
        postOrder(root->right);
        cout<<root->data<<" ";
    }
}

```