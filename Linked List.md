# Linked List 
- Linear data structure
- Stored at a discontinuous location
![This is an image](https://media.geeksforgeeks.org/wp-content/uploads/20220816144425/LLdrawio.png)

# Why Linked List? 
## Arrary limitations
- The size of the arrays is fixed
- Insertion of a new element / Deletion of a existing element in an array of elements is expensive:
  - Example: id[] = [1, 2, 3, 4, 5]，if insert an element at 2th position, we have to move all the elements after 1.
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
Simple Linked List – move or traverse the linked list in only one direction
Doubly Linked List – move or traverse the linked list in both directions (Forward and Backward)
Circular Linked List – the last node of the linked list contains the link of the first/head node of the linked list in its next pointer and the first/head node contains the link of the last node of the linked list in its prev pointer

# Representation of Linked Lists
- Represented by a pointer to the first node of the linked list. 
- The first node is called the head of the linked list. 
- empty linked list, then the value of the head points to NULL. 
- Each node in a list consists of at least two parts: 
  - A Data Item (we can store integer, strings, or any type of data).
  - Pointer (Or Reference) to the next node (connects one node to another) or An address of another node
In C, represent a node using structures

# Implement
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


