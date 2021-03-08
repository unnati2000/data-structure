## Add in the beginning

```
void addAtBeg(int data){

    if(head == NULL){
        cout<<"Linked List does not exist"<<endl;
    }else{
        struct Node *temp = new Node();
        temp->data = data;
        temp->next = head;
        head = temp;
    }
}
```

## Insert at a given location

```
    void insert(int pos, int data){

    struct Node *temp = new Node();
    temp->data = data;
    struct Node *t = head;

    for(int i = 0; i < pos-1; i++){
        t = t->next;
        if(t->next == NULL){
            cout<<"Can't insert"<<endl;
        }
    }

    temp->next = t->next;
    t->next = temp;

}
```

## Append a node

```
void addAtTheEnd(int data){

    struct Node *temp = new Node();
    temp->data = data;
    temp->next = NULL;
    if(head == NULL){
        head = temp;
    }else{
         struct Node *r = head;
         while(r->next!=NULL){
             r = r->next;
         }
         r->next = temp;

    }
}

```
