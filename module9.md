## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```c
#include <stdio.h>
#define MAX 5  
int stack[MAX];
int top = -1;  
void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
    }
}
void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("Popped element: %d\n", stack[top]);
        top--;
    }
}
int main() {
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);
    display();
    pop();
    display();
    return 0;
}
```
## Output:
![alt text](image-8.png)
## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

## EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```c
#include <stdio.h>
#define MAX 5  
float stack[MAX];  
int top = -1;  
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");  
    } else {
        top++;  
        stack[top] = value;  
        printf("Element %.2f pushed onto the stack\n", value);
    }
}
int main() {
    float value;
    printf("Enter a number to push onto the stack: ");
    scanf("%f", &value);
    push(value);
    printf("Enter another number to push onto the stack: ");
    scanf("%f", &value);
    push(value);
    printf("Enter another number to push onto the stack: ");
    scanf("%f", &value);
    push(value);
    printf("Stack after pushing elements:\n");
    for (int i = top; i >= 0; i--) {
        printf("%.2f ", stack[i]);
    }
    printf("\n");
    return 0;
}
```
## Output:
![alt text](image-9.png)
## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```c
#include <stdio.h>
#define MAX 5  
int queue[MAX];
int front = -1, rear = -1;
void display() {
    if (front == -1) {
        printf("Queue is empty\n");  
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);  
        }
        printf("\n");
    }
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  
    } else {
        if (front == -1) {  
            front = 0;
        }
        rear++;  
        queue[rear] = value;
        printf("Enqueued %d to the queue\n", value);
    }
}
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow\n");  
    } else {
        printf("Dequeued %d from the queue\n", queue[front]);
        front++; 
        if (front > rear) {  
            front = rear = -1;
        }
    }
}
int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();  
    dequeue(); 
    display();  
    return 0;
}
```
## Output:
![alt text](image-10.png)
## Result:
Thus, the program to display queue elements using array is verified successfully.


 
## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```c
#include <stdio.h>
#define MAX 5  
int queue[MAX];
int front = -1, rear = -1;
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  
    } else {
        if (front == -1) { 
            front = 0;
        }
        rear++;  
        queue[rear] = value;
        printf("Inserted %d into the queue\n", value);
    }
}
void display() {
    if (front == -1) {
        printf("Queue is empty\n");  
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);  
        }
        printf("\n");
    }
}
int main() {
    enqueue(10);  
    enqueue(20);  
    enqueue(30);  
    display();  
    return 0;
}
```
## Output:
![alt text](image-11.png)
## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY
## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:
```c
#include <stdio.h>
#define MAX 5 
int queue[MAX];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow\n");  
    } else {
        printf("Deleted %d from the queue\n", queue[front]);  
        front++;  
        if (front > rear) {
            front = rear = -1;  
        }
    }
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  
    } else {
        if (front == -1) {  
            front = 0;
        }
        rear++; 
        queue[rear] = value;
        printf("Inserted %d into the queue\n", value);
    }
}
void display() {
    if (front == -1) {
        printf("Queue is empty\n"); 
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]); 
        }
        printf("\n");
    }
}
int main() {
    enqueue(10);  
    enqueue(20);  
    enqueue(30);  
    display(); 
    dequeue();  
    display(); 
    return 0;
}
```
## Output:
![alt text](image-12.png)
## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
