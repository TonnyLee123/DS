# Stack
- linear data structure 
- Last In First Out (LIFO).
  -  last element inserted inside the stack is removed first.  

## Basic Operations of Stack

Push: Add an element to the top of a stack
Pop: Remove an element from the top of a stack
top: Returns the top element of the stack.
IsEmpty: Check if the stack is empty
IsFull: Check if the stack is full
Peek: Get the value of the top element without removing it
size() returns the size of stack


## Working of Stack Data Structure
A pointer called TOP is used to keep track of the top element in the stack.
When initializing the stack, we set its value to -1 so that we can check if the stack is empty by comparing TOP == -1.
On pushing an element, we increase the value of TOP and place the new element in the position pointed to by TOP.
On popping an element, we return the element pointed to by TOP and reduce its value.
Before pushing, we check if the stack is already full
Before popping, we check if the stack is already empty

##push
```c
void push(int x){
    if(top==MAX_SIZE-1){
        printf("stack overflow\n");
        return;
    }
    top=top+1;
    A[top]=x;
    //簡化成 A[++top]=x; increment before assignment
};

```
##pop
```c
void pop(){
    //if empty stack
    if(top==MAX_SIZE-1){
        printf("no element to pop\n");
        return;
    }
    top=top-1;
};
```
##print
```c
void print(){
    int i;
    for(i=0; i<=top; i++){
        printf("%d", A[i]);
    }
};

```
##top
```c
int Top(){
    return A[top];
};

```
##
```c
#define MAX_SIZE 101
int A[MAX_SIZE];
int top=-1;

int main()
{
    push(2);//2
    push(5);//2 5
    push(7);// 2 5 7
    pop();  //2 5
    push(9);// 2 5 9
    print();

    return 0;
};
```
```
push() 	O(1)
pop()   	O(1)
isEmpty() 	O(1)
size()	O(1)
```
Types of Stacks:
Register Stack: a memory element present in the memory unit and can handle a small amount of data only. The height of the register stack is always limited as the size of the register stack is very small compared to the memory.
Memory Stack: handle a large amount of memory data. The height of the memory stack is flexible as it occupies a large amount of memory data. 

Applications of the stack:
Infix to Postfix /Prefix conversion
Redo-undo features at many places like editors, photoshop.
Forward and backward features in web browsers
Used in many algorithms like Tower of Hanoi, tree traversals, stock span problems, and histogram problems.
Backtracking is one of the algorithm designing techniques. Some examples of backtracking are the Knight-Tour problem, N-Queen problem, find your way through a maze, and game-like chess or checkers in all these problems we dive into someway if that way is not efficient we come back to the previous state and go into some another path. To get back from a current state we need to store the previous state for that purpose we need a stack.
In Graph Algorithms like Topological Sorting and Strongly Connected Components
In Memory management, any modern computer uses a stack as the primary management for a running purpose. Each program that is running in a computer system has its own memory allocations
String reversal is also another application of stack. Here one by one each character gets inserted into the stack. So the first character of the string is on the bottom of the stack and the last element of a string is on the top of the stack. After Performing the pop operations on the stack we get a string in reverse order.


Implementation of Stack: 
There are two ways to implement a stack

Using array
Using linked list
```c
 data){
    struct Node* new_node=(struct Node*)malloc(sizeof(struct Node));
    new_node->data=data;
    new_node->next=top;
    top=new_node;
};

void pop(){
    struct Node* temp;
    if(top==NULL) return;//empty stack
    temp=top;
    top=temp->next;
    free(temp);
   
};
int main()
{
    printf("Hello World");

    return 0;
}

```
