## Merge Two sorted linked list

```
Node* sortedMerge(Node* head_A, Node* head_B){

    Node *first = head_A, *second = head_B;
    Node *head = NULL, *tail = NULL;
    int d;
    while(first!=NULL && second!=NULL){

        if(first->data > second->data){
            d = second->data;
            second = second->next;
        }else{
            d = first->data;
            first = first->next;
        }

        Node *temp = new Node(d);
        if(head == NULL){
            head = temp;
            tail = temp;
        }else{
           tail->next = temp;
          tail = temp;
        }
    }

    while(first!=NULL){
        Node *temp = new Node(first->data);
        tail->next = temp;
        tail = temp;
        temp = tail;
        first = first->next;
    }

    while(second!=NULL){
        Node *temp = new Node(second->data);
        tail->next = temp;
        tail = temp;
        second = second->next;
    }
    return head;
}

```
