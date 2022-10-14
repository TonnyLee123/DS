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
