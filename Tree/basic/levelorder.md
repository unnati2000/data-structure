## Level Order Traversal

It uses queue to store and print data

```
void levelOrder(Node *root){
    
    if(root == NULL){
        return;
    }
    
    queue <Node*> q;
    q.push(root);
    
    while(q.empty() == false){
        
        Node *curr = q.front();
        q.pop();
        cout<<curr->data<<" ";
        
        if(curr->left!=NULL){
            q.push(curr->left);
        }
        
        if(curr->right!=NULL){
            q.push(curr->right);
        }
    }
    
}

```

### OUTPUT
```
10 20 30 40 50
```


## Level Order Traversal in a line

```
void levelOrder(Node *root){
    
    if(root == NULL){
        return;
    }
    queue <Node*> q;
    q.push(root);
    
   q.push(NULL);
   
   while(q.size() > 1){
       
       
       Node *curr = q.front();
       q.pop();
       
       if(curr == NULL){
           cout<<endl;
           q.push(NULL);
           continue;
       }
       
       cout<<curr->data<<" ";
       
       if(curr->left!=NULL){
           q.push(curr->left);
       }
       if(curr->right!=NULL){
           q.push(curr->right);
       }
       
   }
    
}

```

### OutPut
```
10 
20 30 
50 40 

```