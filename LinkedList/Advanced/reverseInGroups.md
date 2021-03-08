## Reverse in group of given size

```
struct node *reverse (struct node *head, int k){

    if(head == NULL || k == 1){
        return head;
    }

    struct node *t = head;
    int count  = 0;
    while(t!=NULL){
        count++;
        t = t->next;
    }

    struct node *temp = new struct node(0);
    temp->next = head;
    struct node  *p = temp, *c = temp, *n = temp;

    while(count >=k){
        c = p->next;
        n = c->next;
        for(int i = 1; i < k; i++){
            c->next = n->next;
            n->next = p->next;
            p->next = n;
            n = c->next;
        }
        p = c;
        count = count-k;
    }

    return temp->next;
}

```
