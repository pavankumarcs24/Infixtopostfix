#include<stdio.h>
#define MAX 3

int queue[MAX];
int front = -1 , rear = -1 ;

int isFull(){
    return rear == MAX -1 ;
}
int isEmpty(){
    return front == -1 || front > rear ;
}
void enqueue(int element){
    if(isFull()){
        printf("Queue Overflow!Cannot insert new element\n");
    }else {
        if(front==-1)
            front = 0 ;
        rear ++ ;
        queue[rear] = element ;
        printf("%d is inserted into the element",element);

    }
}
void dequeue(){
    if(isEmpty()){
        printf("Queue Underflow ! Queue is Empty \n");
    }else{
        printf("%d is deleted from the stack",queue[front]);
        front++;
    }
}
void display(){
    if(isEmpty()){
        printf("Queue is Empty\n");
    }else {
        printf("Queue Elements are : ");
        for (int i = front ; i <= rear ; i++){
            printf("%d",queue[i]);
        }
        printf("\n");
    }
}
int main(){
    int choice , element ;
    while(1){
        printf("\n Linear Queue Menu : ");
        printf("\n 1.Enqueue\n 2.Dequeue\n 3.Display \n 4.Exit.\n");
        printf("Enter a choice : ");
        scanf("%d",&choice);

        switch(choice){
            case 1:
                printf("Enter Element to be inserted : ");
                scanf("%d",&element);
                enqueue(element);
                break;
            case 2 :
                dequeue();
                break;
            case 3 :
                display();
                break;
            case 4 :
                printf("Exiting the program..");
                break;
                exit(0);
            default :
                printf("Invalid choice ");

        }
    }
    return 0 ;
}
