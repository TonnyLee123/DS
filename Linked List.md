# Linked List 
- Linear data structure
- Stored at a discontinuous location
![This is an image](https://media.geeksforgeeks.org/wp-content/uploads/20220816144425/LLdrawio.png)

# Why Linked List? 
## Arrary limitations
- The size of the arrays is fixed
- Insertion of a new element / Deletion of a existing element in an array of elements is expensive:
  - Example: id[] = [1, 2, 3, 4, 5]ï¼if insert an element at 2th position, we have to move all the elements after 1.
  - to delete 2 in id[], everything after 2 has to be moved due to thisforword
  
# Advantages of Linked Lists over arrays
Dynamic Array.
Ease of Insertion/Deletion.

# Drawbacks of Linked Lists
- Random access is not allowed. 
  - Access elements sequentially starting from the head node. So we cannot do a binary search with linked lists efficiently with its default implementation. 
- Extra memory space for a pointer. 
- Not cache friendly.

# Types of Linked Lists:
Simple Linked List â move or traverse the linked list in only one direction
Doubly Linked List â move or traverse the linked list in both directions (Forward and Backward)
Circular Linked List â the last node of the linked list contains the link of the first/head node of the linked list in its next pointer and the first/head node contains the link of the last node of the linked list in its prev pointer

# Representation of Linked Lists
- Represented by a pointer to the first node of the linked list. 
- The first node is called the head of the linked list. 
- empty linked list, then the value of the head points to NULL. 
- Each node in a list consists of at least two parts: 
  - A Data Item (we can store integer, strings, or any type of data).
  - Pointer (Or Reference) to the next node (connects one node to another) or An address of another node
In C, represent a node using structures

# Linked List Implementations
# node
```c
struct Node{
  int data;
  struct Node* next;
};
```
## Construction of a simple linked list with 3 nodes:
```c
int main()
{   
    /* Initialize nodes */
    struct Node* head=NULL;
    struct Node* second=NULL;
    struct Node* third=NULL;
    /* Allocate memory in the heap*/
    head=(struct Node*)malloc(sizeof(struct Node));
    second=(struct Node*)malloc(sizeof(struct Node));
    third=(struct Node*)malloc(sizeof(struct Node));
    /* Assign data values */
    head->data=1;
    second->data=3;
    third->data=5;
    /* Connect nodes */
    head->next=second;
    second->next=third;
    third->next=NULL;
    return 0;
}
```
## Traversal of a Linked List
Traverse the created list and print the data of each node.
```c
// keep moving the temp node to the next one and display its contents.
//When temp is NULL, we know that we have reached the end of the linked list so we get out of the while loop.
void print(struct Node *head)
{
   struct Node* temp=head;
   while(temp!=NULL){
       printf("%d ", temp->data);
       temp=temp->next;
   }
}

print(head);

//output: 1 3 5
```
## Insert Elements
### 1. Insert at the beginning
- Allocate memory for new node
- Store data
- Change next of new node to point to head
- Change head to point to recently created node
```
void insert_b(int data){
    struct Node* new_node=(struct Node*)malloc(sizeof(struct Node));
    new_node->data=data;
    new_node->next=head;
    head=new_node;
};
```
### 2.  Insert at the End
Allocate memory for new node
Store data
Traverse to last node
Change next of last node to recently created node
```c
void insert_e(int data)
{
    struct Node* new_node=(struct Node*)malloc(sizeof(struct Node));
    struct Node* temp=(struct Node*)malloc(sizeof(struct Node));
    temp=head;
    //ç¨while loopä½¿temp = åæ¸ç¬¬äºånode(åæ¬çæå¾ä¸å)
    /*
    while(temp!=NULL){ //é¯èª¤:æå¾temp=NULL 
        temp=temp->next;
    }
    */
    while(temp->next!=NULL){
        temp=temp->next;
    }
    new_node->data=data;
    new_node->next=NULL;
    temp->next=new_node;
};
```
### 3. Insert at the Middle
-Allocate memory and store data for new node
-Traverse to node just before the required position of new node
-Change next pointers to include new node in between

-Check if the given previous node is NULL or not.
-allocate a new node and Assign the data to the new node
And then make the next of new node as the next of previous node. 
Finally, move the next of the previous node as a new node.
```c
#include <stdio.h>
#include <stdlib.h>
struct Node{
    int data;
    struct Node* next;
};

void insert(int,int);
void print(struct Node*);

struct Node* head;
int main()
{   
    head=NULL;
    insert(5, 1);
    insert(6, 2);
    print(head);

    return 0;
}
void insert(int data, int position){
    struct Node* new_node=(struct Node*)malloc(sizeof(struct Node));
    struct Node* pre_node=(struct Node*)malloc(sizeof(struct Node));
    pre_node=head;
    
    if(position==1){
        new_node->data=data;
        new_node->next=head;
        head=new_node;
    }
    else{
        
        for(int i=0;i<position-2;i++){
            pre_node=pre_node->next;
        }
        if(pre_node!=NULL){
            new_node->data=data;
            new_node->next=pre_node->next;
            pre_node->next=new_node;
        }else{printf("pre_node doesn't exist");}
    }};
    

void print(struct Node* head)
{
   struct Node* temp=head;
   while(temp!=NULL){
       printf("%d ", temp->data);
       temp=temp->next;
   }
};
```
