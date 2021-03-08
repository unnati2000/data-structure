## Rotate a linked list

```
Node* rotate(Node* head, int k){

     if(head == NULL || k == 0){
        return head;
    }

    struct Node *t = head;
    int len = 1;

    while(t->next){
        t = t->next;
        len++;
    }

    // making a circular linked list
    t->next = head;

    // if k > len
    k = k%len;
    k = len-k;

    while(k--){
        t = t->next;
    }

    head = t->next;
    t->next = NULL;

    return head;
}

```
