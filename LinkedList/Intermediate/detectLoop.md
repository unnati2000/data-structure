## Detect a loop in a linked list

```
int detectloop(Node *head) {

    Node *fast = head, *slow = head;
    while(slow && fast && fast->next!=NULL){
        slow = slow->next;
        fast = fast->next->next;
    }
    if(fast == slow){
        return 1;
    }else{
        return 0;
    }
}

```
