## Delete by data

```
void deleteByData(int data){
    struct Node *curr , *prev, *t;
    for(curr = head, prev = NULL; curr->next!=NULL; prev = curr, curr = curr->next){
        if(curr->data == data){

            if(prev == NULL){
                t = curr;
                curr = curr->next;
                free(t);
                prev = curr;
                head = prev;
            }else{
                t = curr;
                prev->next = curr->next;
                curr = prev;
                free(t);
            }
        }
    }
}

```

## Delete by position

```
    int delete_by_pos(int pos){

    struct Node *f = head;
    struct Node *s = NULL;
    int x;

    if(pos == 0){
        s = head;
        x = head->data;
        head = head->next;
        delete(s);
        return x;
    }else{

        for(int i = 0; i < pos; i++){
            s = f;
            f = f->next;
        }
        s->next = f->next;
        x = f->data;
        delete(f);
        return x;
    }

}

```

## Length of linked list

```
    int length(){

        if(head == NULL){
            cout<<"Linked list does not exist"<<endl;
            return 0;
        }else{

            struct Node *t = head;
            int count = 0;
            while(t!=NULL){
                count++;
                t = t->next;
            }
            return count;
        }
    }

```

## Display a linked list

```
    void display(){
    if(head == NULL){
        cout<<"Linked List does not exist"<<endl;
    }else{
        struct Node *t = head;
        while(t!=NULL){
            cout<<t->data<<" ";
            t = t->next;
        }
        cout<<endl;
    }
}

```
