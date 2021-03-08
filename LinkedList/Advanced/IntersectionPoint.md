## Intersection point in two linked list

```
int intersectPoint(Node* head1, Node* head2){

    int len1 = 0, len2 = 0;
    Node *first = head1, *second = head2;
    while(first!=NULL){
        len1++;
        first = first->next;
    }
    while(second!=NULL){
        len2++;
        second = second->next;
    }

    if(len1>len2){
        int d = len1-len2;
        while(d>0){
            first = first->next;
            second = second->next;
            if(first == second){
                break;
            }
            d--;
        }
        int dt = first->data;
        return dt;
    }else{

        int d = len2-len1;
        while(d > 0){
            first = first->next;
            second = second->next;
            if(first == second){
                break;
            }
            d--;
        }
        int dt = first->data;
        return dt;
    }
}

```
