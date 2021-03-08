## Middle Element in a linked list

```
int middle_element(){
    struct Node *fast = head, *slow = head;
    while(fast->next->next != NULL){
        fast = fast->next->next;
        slow = slow->next;
    }
    return slow->data;
}
```

## Reversing a linked list

```
void reverse(){
    struct Node *prev, *curr, *next;
    curr = head;
    prev=NULL;

    while(curr!=NULL){

        next = curr->next;
        curr->next = prev;

        prev = curr;
        curr = next;
    }

    head = prev;
    display();
}


```

## Find nth node from the end

```
int find_nth_node_from_end(int n){

    struct Node *f = head;
    struct Node *s = head;
    int count = 0;

    while(count <= n-1){
        count = count+1;
        f = f->next;
    }

    while(f!=NULL){
        f = f->next;
        s = s->next;
    }
    return s->data;

}

```
