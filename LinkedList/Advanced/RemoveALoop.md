## Remove a loop in a Linked list

```
void removeLoop(Node* head){
    if(head == NULL || head->next == NULL){
        return;
    }
    struct Node *f = head, *s = head;
    while(s && f && f->next){
        s = s->next;
        f = f->next->next;
    }

    if(f == s){
        s = head;
        while(s->next != f->next){
            s = s->next;
            f = f->next;
        }

        f->next = NULL;
    }
}

```
