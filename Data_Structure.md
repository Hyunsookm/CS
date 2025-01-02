# Data Structure
## 리스트(List)
#### 배열(Array)
- 정의: 
-- 같은 데이터 타입의 값들을 하나의 묶음으로 저장할 수 있는 자료구조.
- 특징:
-- 특정 데이터 타입의 요소를 일정한 크기로 메모리 공간에 연속적으로 저장.
-- 인덱스를 통해 각 요소에 접근.

##### 고정 크기 배열(Fixed-size Array)
- 정의:
-- 배열의 크기가 선언 시점에 고정되어, 이후에 크기를 변경할 수 없는 배열.
- 특징:
-- 배열 크기가 고정되어 있어서 메모리 할당도 한 번만 이루어진다.
- 장점:
-- 연속된 메모리 공간을 차지하기 때문에 접근 속도가 빠르다.
- 단점:
-- 배열의 크기를 변경할 수 없기 때문에 유동적인 크기 조정이 불가능하다.
-- 메모리 낭비가 발생할 수 있다.
- 예시:
```c
//c에서의 고정 크기 배열
int arr[10]; // 고정 크기 배열, 크기 10
```

##### 동적 배열(Dynamic Array)
- 정의:
-- 배열의 크기를 동적으로 변경할 수 있는 배열.
- 특징:
-- 프로그램 실행 중에 메모리가 동적으로 할당되고 해제된다.
- 장점:
-- 배열의 크기를 필요에 따라 유동적으로 조정할 수 있다.
- 단점:
-- 메모리 할당 및 해제 과정에서 추가적인 시간과 자원이 필요하다.
- 예시:
```c
//c에서의 동적 크기 배열 
int* arr = (int*)malloc(sizeof(int) * 10); // 동적 배열, 크기 10
```
```java
//Java에서의 동적 크기 배열
ArrayList<Integer> dynamicArray = new ArrayList<>(); //동적 배열 생성
````
//정적, 동적 배열에서 데이터 접근 속도 등,, 차이

#### 연결 리스트(Linked List)
- 정의: 
-- 같은 데이터 타입의 값들을 하나의 묶음으로 저장할 수 있는 자료구조.
- 특징:
-- 배열처럼 고정된 크기가 아니라, 노드가 추가되거나 삭제되면서 크기가 동적으로 변한다.
-- 각 노드는 메모리의 다른 위치에 저장되며, 인덱스가 아닌 포인터를 통해 연결된다.
-- 데이터 요소가 순차적으로 연결된 구조이다.

##### 단일 연결 리스트 (Singly-Linked List)
- 정의: 
-- 각 노드가 데이터와 다음 노드를 가리키는 포인터를 가진 연결 리스트.
- 특징:
-- 각 노드는 다음 노드를 가리키는 포인터만을 가진다.
-- 데이터를 찾기 위해 첫 번째 노드부터 차례대로 탐색해야 한다. 
- 장점:
-- 메모리 사용이 효율적이며, 동적으로 크기를 조정할 수 있다.
- 단점:
-- 검색 속도가 느리며, 단방향으로만 탐색이 가능하다.
- 예시:
```c
//c에서의 Singly-Linked List
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void append(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;
    new_node->data = data;
    new_node->next = NULL;

    if (*head == NULL) {
        *head = new_node;
        return;
    }
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
}

void display(struct Node* node) {
    while (node != NULL) {
        printf("%d -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    append(&head, 1);
    append(&head, 2);
    append(&head, 3);
    display(head);
    return 0;
}

```
```java
//Java에서의 Singly-Linked List
class Node {
    int data;
    Node next;
    
    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class SinglyLinkedList {
    Node head;

    public void append(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newNode;
    }

    public void display() {
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " -> ");
            current = current.next;
        }
        System.out.println("NULL");
    }

    public static void main(String[] args) {
        SinglyLinkedList list = new SinglyLinkedList();
        list.append(1);
        list.append(2);
        list.append(3);
        list.display();
    }
}

````

##### 이중 연결 리스트 (Doubly-Linked List)
- 정의: 
-- 각 노드가 데이터와 이전 노드, 다음 노드를 가리키는 포인터를 가진 연결 리스트.
- 특징:
-- 각 노드는 이전 노드와 다음 노드를 모두 가리킨다.
-- 양쪽 끝에서 데이터의 삽입 및 삭제가 효율적이다.

- 장점:
-- 양방향 탐색이 가능하여 유연하다.
- 단점:
-- 메모리 사용량이 증가하며, 포인터 관리가 복잡하다.
- 예시:
```c
//C에서의 Doubly-Linked List
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

void append(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;
    new_node->data = data;
    new_node->next = NULL;

    if (*head == NULL) {
        new_node->prev = NULL;
        *head = new_node;
        return;
    }
    while (last->next != NULL) {
        last = last->next;
    }
    last->next = new_node;
    new_node->prev = last;
}
```
```java
//Java에서의 Doubly Linked List
class Node {
    int data;
    Node prev;
    Node next;

    public Node(int data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}

public class DoublyLinkedList {
    Node head;

    public void append(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node current = head;
        while (current.next != null) {
            current = current.next;
        }
        current.next = newNode;
        newNode.prev = current;
    }
```
##### 원형 연결 리스트 (Circular-Linked List)
- 정의: 
-- 마지막 노드가 첫 번째 노드를 가리키는 연결 리스트이다. 리스트의 끝이 아니라 첫 번째 노드로 돌아간다.
- 특징:
-- 마지막 노드가 첫 번째 노드를 가리키며 순환한다.
-- 리스트의 끝이 없으며, 순차적으로 순환한다.

- 장점:
-- 주기적인 작업에 적합하다.
- 단점:
-- 무한 루프가 발생할 수 있으며 종료 조건을 명확히 해야 한다.
- 예시:
```c
//C에서의 Circular LinkedList
struct Node {
    int data;
    struct Node* next;
};

void append(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* last = *head;
    new_node->data = data;
    new_node->next = *head;

    if (*head == NULL) {
        *head = new_node;
        return;
    }
    while (last->next != *head) {
        last = last->next;
    }
    last->next = new_node;
}
```
```java
//Java에서의 Circular LinkedList
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class CircularLinkedList {
    Node head;

    public void append(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            newNode.next = head;
            return;
        }
        Node current = head;
        while (current.next != head) {
            current = current.next;
        }
        current.next = newNode;
        newNode.next = head;
    }
}
```

##### 다중 연결 리스트 (Multi-Linked List)
- 정의: 
-- 각 노드가 데이터와 이전 노드, 다음 노드를 가리키는 포인터를 가진 연결 리스트.
- 특징:
-- 각 노드는 다른 연결 리스트를 가리킬 수 있다.
-- 다수의 레벨을 가진 리스트로, 각 노드가 다중 포인터를 가질 수 있다.
- 장점:
-- 다양한 데이터 구조를 표현하고 처리할 수 있다.

- 예시:
```c
//C에서의 Multi-Linked List
typedef struct Node {
    int data;           // 데이터 필드
    struct Node* next;  // 다음 노드를 가리키는 포인터
    struct Node* sublist; // 서브 리스트를 가리키는 포인터
} Node;

void insertNode(Node** head, int data) {
    Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
    } else {
        Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}
int main(){
    Node* head = NULL;
    insertNode(&head, 10);
    insertNode(&head, 20);

    Node* sublistHead = NULL;
    insertNode(&sublistHead, 100);
    insertNode(&sublistHead, 200);
    // 서브 리스트를 20번 노드에 연결
    head->next->sublist = sublistHead;
}
```
```java
//Java에서의 Multi-Linked List
class Node {
    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

// 연결 리스트
class LinkedList {
    Node head;

    public LinkedList() {
        head = null;
    }

    // 리스트에 노드 추가
    public void add(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
        } else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;
            }
            temp.next = newNode;
        }
    }
}
```

## Stack
- 정의: 
-- 후입선출(LIFO, Last In First Out)을 따르는 자료구조.
- 특징:
-- 데이터를 쌓아 올리는 형태를 가짐.
-- 데이터의 삽입, 삭제가 top에서만 이루어짐.
-- 주요 연산 : Push(데이터 삽입), Pop(데이터 제거), Peek(데이터 조회)

#### 배열 기반 스택 (Array-based Stack)
- 정의:
-- 배열을 이용하여 스택을 구현한 자료구조이다. 스택의 크기는 고정적이며, 배열의 인덱스를 이용하여 데이터를 삽입하고 삭제한다.
- 특징:
-- 배열의 크기가 한정되어 있어 스택의 크기가 고정된다.
-- 배열의 인덱스를 이용하여 빠르게 데이터에 접근할 수 있다.
- 장점:
-- 구현이 간단하고, 메모리 접근이 빠르다.
- 단점:
-- 크기가 고정되어 있어 크기를 초과하는 데이터 삽입이 불가능하다.
-- 메모리 낭비가 발생할 수 있다.
- 예시:
```c
//c에서의 Array-based Stack
#include <stdio.h>
#include <stdlib.h>

#define MAX 5 // 스택 크기

struct Stack {
    int arr[MAX];
    int top;
};

void initStack(struct Stack* stack) {
    stack->top = -1;
}

int isFull(struct Stack* stack) {
    return stack->top == MAX - 1;
}

int isEmpty(struct Stack* stack) {
    return stack->top == -1;
}

void push(struct Stack* stack, int data) {
    if (isFull(stack)) {
        printf("Stack is full\n");
        return;
    }
    stack->arr[++(stack->top)] = data;
}

int pop(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack->arr[(stack->top)--];
}

void display(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return;
    }
    for (int i = stack->top; i >= 0; i--) {
        printf("%d ", stack->arr[i]);
    }
    printf("\n");
}

int main() {
    struct Stack stack;
    initStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    display(&stack);

    printf("Popped: %d\n", pop(&stack));
    display(&stack);

    return 0;
}
```
```java
//Java에서의 Array-based Stack
class ArrayStack {
    private int[] arr;
    private int top;
    private int capacity;

    public ArrayStack(int size) {
        capacity = size;
        arr = new int[capacity];
        top = -1;
    }

    public boolean isFull() {
        return top == capacity - 1;
    }

    public boolean isEmpty() {
        return top == -1;
    }

    public void push(int data) {
        if (isFull()) {
            System.out.println("Stack is full");
            return;
        }
        arr[++top] = data;
    }

    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return arr[top--];
    }

    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return;
        }
        for (int i = top; i >= 0; i--) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        ArrayStack stack = new ArrayStack(5);
        stack.push(10);
        stack.push(20);
        stack.push(30);
        stack.display();

        System.out.println("Popped: " + stack.pop());
        stack.display();
    }
}
```

#### 연결 리스트 기반 스택 (LinkedList-based Stack)
- 정의:
-- 연결리스트를 이용하여 스택을 구현한 자료구조이다. 배열과 달리 동적으로 크기가 조정되며, 스택의 요소들은 각 노드로 연결된다.
- 특징:
-- 스택의 크기가 동적으로 조정되므로 메모리 낭비가 없다.
-- 각 요소는 데이터와 다음 노드를 가리키는 포인터를 가진다.
- 장점:
-- 크기가 동적으로 조정되므로 메모리 낭비가 없고, 크기에 제한이 없다.
- 단점:
-- 배열 기반 스택보다 더 많은 메모리를 소모한다.
- 예시:
```c
//c에서의 LinkedList-based Stack
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void push(struct Node** top, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = data;
    new_node->next = *top;
    *top = new_node;
}

int pop(struct Node** top) {
    if (*top == NULL) {
        printf("Stack is empty\n");
        return -1;
    }
    struct Node* temp = *top;
    int popped_data = temp->data;
    *top = (*top)->next;
    free(temp);
    return popped_data;
}
```
```java
//Java에서의 LinkedList-based Stack
class LinkedListStack {
    private static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    private Node top;

    public LinkedListStack() {
        top = null;
    }

    public boolean isEmpty() {
        return top == null;
    }

    public void push(int data) {
        Node newNode = new Node(data);
        newNode.next = top;
        top = newNode;
    }

    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        int poppedData = top.data;
        top = top.next;
        return poppedData;
    }

    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return;
        }
        Node temp = top;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
```
#### 최소값/최대값 추적 스택 (Min/Max Stack)
- 정의:
-- 스택에서 값을 삽입하고 삭제할 때마다 현재 스택 내 최대값과 최소값을 추적할 수 있도록 설계된 스택이다.
- 특징:
-- 스택에 값을 삽입할 때마다 현재 스택의 최대값과 최소값을 추적한다.
-- 최대값과 최소값을 추적하기 위해 두 번째 스택을 사용한다. 하나는 데이터를 저장하고, 다른 하나는 최대값 또는 최소값을 저장한다.
- 장점:
-- 최대값과 최소값을 O(1) 시간 복잡도로 추적할 수 있다.
- 단점:
-- 최대값과 최소값을 추적하기 위한 추가적인 공간(두 번째 스택)을 사용한다.
- 예시:
```c
//c에서의 Min/Max Stack
#include <stdio.h>
#include <stdlib.h>
#include <limits.h>

struct Stack {
    int *arr;
    int top;
    int *maxStack;
    int *minStack;
    int capacity;
};

void initStack(struct Stack* stack, int capacity) {
    stack->capacity = capacity;
    stack->arr = (int*)malloc(capacity * sizeof(int));
    stack->maxStack = (int*)malloc(capacity * sizeof(int));
    stack->minStack = (int*)malloc(capacity * sizeof(int));
    stack->top = -1;
}

int isFull(struct Stack* stack) {
    return stack->top == stack->capacity - 1;
}

int isEmpty(struct Stack* stack) {
    return stack->top == -1;
}

void push(struct Stack* stack, int data) {
    if (isFull(stack)) {
        printf("Stack is full\n");
        return;
    }
    stack->arr[++(stack->top)] = data;

    if (stack->top == 0) {
        stack->maxStack[stack->top] = data;
        stack->minStack[stack->top] = data;
    } else {
        stack->maxStack[stack->top] = (data > stack->maxStack[stack->top - 1]) ? data : stack->maxStack[stack->top - 1];
        stack->minStack[stack->top] = (data < stack->minStack[stack->top - 1]) ? data : stack->minStack[stack->top - 1];
    }
}

int pop(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    }
    stack->top--;
    return stack->arr[stack->top + 1];
}

int getMax(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack->maxStack[stack->top];
}

int getMin(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return -1;
    }
    return stack->minStack[stack->top];
}

void display(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty\n");
        return;
    }
    for (int i = stack->top; i >= 0; i--) {
        printf("%d ", stack->arr[i]);
    }
    printf("\n");
}

int main() {
    struct Stack stack;
    initStack(&stack, 5);

    push(&stack, 10);
    push(&stack, 20);

    display(&stack);
    printf("Max: %d, Min: %d\n", getMax(&stack), getMin(&stack));

    printf("Popped: %d\n", pop(&stack));
    display(&stack);
    printf("Max: %d, Min: %d\n", getMax(&stack), getMin(&stack));

    return 0;
}

```
```java
//Java에서의 Min/Max Stack
class MaxMinStack {
    private int[] arr;
    private int[] maxStack;
    private int[] minStack;
    private int top;
    private int capacity;

    public MaxMinStack(int size) {
        capacity = size;
        arr = new int[capacity];
        maxStack = new int[capacity];
        minStack = new int[capacity];
        top = -1;
    }

    public boolean isFull() {
        return top == capacity - 1;
    }

    public boolean isEmpty() {
        return top == -1;
    }

    public void push(int data) {
        if (isFull()) {
            System.out.println("Stack is full");
            return;
        }
        arr[++top] = data;

        if (top == 0) {
            maxStack[top] = data;
            minStack[top] = data;
        } else {
            maxStack[top] = Math.max(data, maxStack[top - 1]);
            minStack[top] = Math.min(data, minStack[top - 1]);
        }
    }

    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        top--;
        return arr[top + 1];
    }

    public int getMax() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return maxStack[top];
    }

    public int getMin() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return minStack[top];
    }

    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty");
            return;
        }
        for (int i = top; i >= 0; i--) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        MaxMinStack stack = new MaxMinStack(5);

        stack.push(5);
        stack.push(30);

        stack.display();
        System.out.println("Max: " + stack.getMax() + ", Min: " + stack.getMin());

        System.out.println("Popped: " + stack.pop());
        stack.display();
        System.out.println("Max: " + stack.getMax() + ", Min: " + stack.getMin());
    }
}

```
## Queue
- 정의: 
-- 선입선출(FIFO, First-In-First-Out) 방식으로, 한쪽 끝에서는 데이터를 삽입하고 다른 한쪽 끝에서는 데이터를 삭제하는 자료구조이다.
- 특징:
-- 큐는 일반적으로 front(앞)과 rear(뒤) 포인터를 가지고, 삽입과 삭제 연산을 처리한다.
-- 주요 연산 : Enqueue(데이터 삽입), Dequeue(데이터 제거), Peek(데이터 조회)

#### 배열 기반 큐 (Array-based Queue)
- 정의: 
-- 고정된 크기의 배열을 이용하여 큐를 구현한 자료구조이다.
- 특징:
-- 큐의 크기가 고정되어 있으며, 크기를 초과하는 삽입은 불가능하다.
-- 인덱스를 통해 각 요소에 접근한다.
- 장점:
-- 구현이 간단하고 메모리 접근이 빠르다.
- 단점:
-- 고정된 크기를 사용하므로 크기를 미리 지정해야 한다.
- 예시:
```c
//c에서의 Array-based Queue
#include <stdio.h>
#include <stdbool.h>

#define MAX 5

typedef struct {
    int arr[MAX];
    int front;
    int rear;
} Queue;

void initQueue(Queue *q) {
    q->front = 0;
    q->rear = -1;
}

bool isFull(Queue *q) {
    return q->rear == MAX - 1;
}

bool isEmpty(Queue *q) {
    return q->front > q->rear;
}

void enqueue(Queue *q, int data) {
    if (isFull(q)) {
        printf("Queue is full\n");
        return;
    }
    q->arr[++(q->rear)] = data;
}

int dequeue(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->arr[q->front++];
}

int peek(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->arr[q->front];
}

void display(Queue *q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return;
    }
    for (int i = q->front; i <= q->rear; i++) {
        printf("%d ", q->arr[i]);
    }
    printf("\n");
}

int main() {
    Queue q;
    initQueue(&q);

    enqueue(&q, 10);
```

```java
//java에서의 Array-based Queue
class ArrayQueue {
    private int[] arr;
    private int front, rear, capacity;

    public ArrayQueue(int size) {
        capacity = size;
        arr = new int[capacity];
        front = 0;
        rear = -1;
    }

    public boolean isFull() {
        return rear == capacity - 1;
    }

    public boolean isEmpty() {
        return front > rear;
    }

    public void enqueue(int data) {
        if (isFull()) {
            System.out.println("Queue is full");
            return;
        }
        arr[++rear] = data;
    }

    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return arr[front++];
    }

    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        return arr[front];
    }

    public void display() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return;
        }
        for (int i = front; i <= rear; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        ArrayQueue queue = new ArrayQueue(5);

        queue.enqueue(10);
        queue.enqueue(20);
        queue.display();
    }
}

```


#### 순환 큐 (Circular Queue)
- 정의: 
-- 큐의 끝과 앞이 연결되어 있는 큐로, 배열을 이용해 구현한다.
- 특징:
-- 배열의 마지막이 첫 번째와 연결되어, 큐의 앞과 뒤가 서로 연결된다.
-- 배열이 꽉 찬 상태에서 앞쪽에 공간이 남으면, 그 공간을 다시 사용할 수 있다.
-- 인덱스를 통해 각 요소에 접근.
- 장점:
-- 고정된 크기의 배열을 이용해 메모리 낭비가 없음.
- 예시:
```c
//c에서의 Circular Queue
#include <stdio.h>
#include <stdbool.h>

#define MAX 5

typedef struct {
    int arr[MAX];
    int front, rear, size;
} CircularQueue;

void initQueue(CircularQueue* q) {
    q->front = 0;
    q->rear = -1;
    q->size = 0;
}

bool isFull(CircularQueue* q) {
    return q->size == MAX;
}

bool isEmpty(CircularQueue* q) {
    return q->size == 0;
}

void enqueue(CircularQueue* q, int data) {
    if (isFull(q)) {
        printf("Queue is full\n");
        return;
    }
    q->rear = (q->rear + 1) % MAX;
    q->arr[q->rear] = data;
    q->size++;
}

int dequeue(CircularQueue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    int dequeuedData = q->arr[q->front];
    q->front = (q->front + 1) % MAX;
    q->size--;
    return dequeuedData;
}

int peek(CircularQueue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->arr[q->front];
}
```
```java
//Java에서의 Circular Queue
class CircularQueue {
    private int[] arr;
    private int front, rear, size, capacity;

    public CircularQueue(int capacity) {
        this.capacity = capacity;
        arr = new int[capacity];
        front = 0;
        rear = -1;
        size = 0;
    }
      public boolean isFull() {
        return size == capacity;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public void enqueue(int data) {
        if (isFull()) {
            System.out.println("Queue is full");
            return;
        }
        rear = (rear + 1) % capacity;
        arr[rear] = data;
        size++;
    }

    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        int dequeuedData = arr[front];
        front = (front + 1) % capacity;
        size--;
        return dequeuedData;
    }
}
```
#### 연결 리스트 기반 큐 (Linked List-based Queue)
- 정의:
-- 연결리스트를 이용하여 큐를 구현한 자료구조이다. 크기가 동적으로 조정되며, 큐의 앞과 뒤에서 삽입과 삭제가 이루어진다.
- 특징:
-- 연결리스트의 각 노드가 데이터를 저장하고, 다음 노드를 가리킨다.
-- 큐의 앞(front)과 뒤(rear) 포인터를 통해 삽입과 삭제가 이루어진다.
- 장점:
-- 큐의 크기가 동적으로 조정된다.
- 단점:
-- 배열 기반 큐보다 메모리를 추가로 사용한다.
-- 메모리 낭비가 발생할 수 있다.
- 예시:
```c
//c에서의 LinkedList-based Queue
#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node* next;
} Node;

typedef struct {
    Node* front;
    Node* rear;
} Queue;

void initQueue(Queue* q) {
    q->front = q->rear = NULL;
}

int isEmpty(Queue* q) {
    return q->front == NULL;
}

void enqueue(Queue* q, int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;

    if (isEmpty(q)) {
        q->front = q->rear = newNode;
    } else {
        q->rear->next = newNode;
        q->rear = newNode;
    }
}
int peek(Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->front->data;
}
}

int dequeue(Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    Node* temp = q->front;
    int dequeuedData = temp->data;
    q->front = q->front->next;
    free(temp);
    return dequeuedData;
}
```
```java
//c에서의 LinkedList-based Queue
class LinkedListQueue {
    private static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    private Node front, rear;

    public LinkedListQueue() {
        front = rear = null;
    }

    public boolean isEmpty() {
        return front == null;
    }

    public void enqueue(int data) {
        Node newNode = new Node(data);
        if (isEmpty()) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
    }

    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
            return -1;
        }
        int dequeuedData = front.data;
        front = front.next;
        if (front == null) {
            rear = null; // 큐가 비어있으면 rear도 null로 설정
        }
        return dequeuedData;
    }
}
```
#### 우선순위 큐 (Priority Queue)
- 정의: 
-- 일반적인 큐와 달리, 우선순위(priority)가 높은 요소가 먼저 처리되는 큐이다.
- 특징:
-- 우선순위가 높은 항목이 먼저 제거된다.
-- 동일한 우선순위의 항목은 삽입된 순서대로 처리될 수 있다.

##### 배열기반 우선순위 큐
- 정의:
-- 배열의 크기가 선언 시점에 고정되어, 이후에 크기를 변경할 수 없는 배열.
- 특징:
-- 데이터가 삽입될 때마다 우선순위에 맞게 위치를 정렬한다.
-- 삽입 시 O(n) 의 시간 복잡도가 발생할 수 있다.
- 장점:
-- 직접적인 인덱스 접근이 가능하여 데이터를 관리하는 데 편리할 수 있다.
- 단점:
-- 삽입 시 비효율적이다. 데이터를 삽입할 때마다 우선순위에 맞게 배열을 정렬해야 하므로 O(n) 시간 복잡도를 가진다.
-- 큐의 크기가 커지면 메모리 사용이 비효율적일 수 있다.

- 예시:
```c
//c에서의 Array-based Queue
#include <stdio.h>
#include <stdlib.h>

// 힙의 최대 크기
#define MAX 100

// 우선순위 큐를 나타내는 구조체
typedef struct {
    int arr[MAX];
    int size;
} PriorityQueue;

// 우선순위 큐 초기화
void init(PriorityQueue *pq) {
    pq->size = 0;
}

// 부모 인덱스 구하기
int parent(int i) {
    return (i - 1) / 2;
}

// 왼쪽 자식 인덱스 구하기
int leftChild(int i) {
    return 2 * i + 1;
}

// 오른쪽 자식 인덱스 구하기
int rightChild(int i) {
    return 2 * i + 2;
}

// 두 요소를 교환하는 함수
void swap(PriorityQueue *pq, int i, int j) {
    int temp = pq->arr[i];
    pq->arr[i] = pq->arr[j];
    pq->arr[j] = temp;
}

// 힙을 구성하는 함수 (Max-Heap)
void heapify(PriorityQueue *pq, int i) {
    int largest = i;
    int left = leftChild(i);
    int right = rightChild(i);

    if (left < pq->size && pq->arr[left] > pq->arr[largest]) {
        largest = left;
    }
    if (right < pq->size && pq->arr[right] > pq->arr[largest]) {
        largest = right;
    }
    if (largest != i) {
        swap(pq, i, largest);
        heapify(pq, largest);
    }
}

// 요소를 우선순위 큐에 삽입하는 함수
void insert(PriorityQueue *pq, int value) {
    if (pq->size == MAX) {
        printf("Priority Queue is full\n");
        return;
    }
    
    pq->arr[pq->size] = value;
    int i = pq->size;
    pq->size++;
    
    // 삽입한 값을 올바른 위치에 배치
    while (i > 0 && pq->arr[parent(i)] < pq->arr[i]) {
        swap(pq, i, parent(i));
        i = parent(i);
    }
}

// 우선순위 큐에서 최대값을 추출하는 함수
int extractMax(PriorityQueue *pq) {
    if (pq->size <= 0) {
        printf("Priority Queue is empty\n");
        return -1; // 빈 큐
    }
    
    if (pq->size == 1) {
        pq->size--;
        return pq->arr[0];
    }
    
    int root = pq->arr[0];
    pq->arr[0] = pq->arr[pq->size - 1];
    pq->size--;
    
    heapify(pq, 0);
    
    return root;
}

// 큐의 최대값을 반환하는 함수
int getMax(PriorityQueue *pq) {
    if (pq->size <= 0) {
        printf("Priority Queue is empty\n");
        return -1;
    }
    return pq->arr[0];
}

// 큐 출력 함수
void printQueue(PriorityQueue *pq) {
    for (int i = 0; i < pq->size; i++) {
        printf("%d ", pq->arr[i]);
    }
    printf("\n");
}
```

```java
//java에서의 Array-based Queue
public class PriorityQueue {
    private int[] arr;
    private int size;
    private int capacity;

    // 큐의 크기를 설정하는 생성자
    public PriorityQueue(int capacity) {
        this.capacity = capacity;
        this.size = 0;
        this.arr = new int[capacity];
    }

    // 부모 인덱스 구하기
    private int parent(int i) {
        return (i - 1) / 2;
    }

    // 왼쪽 자식 인덱스 구하기
    private int leftChild(int i) {
        return 2 * i + 1;
    }

    // 오른쪽 자식 인덱스 구하기
    private int rightChild(int i) {
        return 2 * i + 2;
    }

    // 두 요소를 교환하는 함수
    private void swap(int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    // 힙 속성을 유지하는 함수
    private void heapify(int i) {
        int largest = i;
        int left = leftChild(i);
        int right = rightChild(i);

        if (left < size && arr[left] > arr[largest]) {
            largest = left;
        }
        if (right < size && arr[right] > arr[largest]) {
            largest = right;
        }
        if (largest != i) {
            swap(i, largest);
            heapify(largest);
        }
    }

    // 큐에 삽입하는 함수
    public void insert(int value) {
        if (size == capacity) {
            System.out.println("Priority Queue is full");
            return;
        }

        arr[size] = value;
        int i = size;
        size++;

        while (i > 0 && arr[parent(i)] < arr[i]) {
            swap(i, parent(i));
            i = parent(i);
        }
    }

    // 최대값을 추출하는 함수
    public int extractMax() {
        if (size <= 0) {
            System.out.println("Priority Queue is empty");
            return -1;
        }
        if (size == 1) {
            size--;
            return arr[0];
        }

        int root = arr[0];
        arr[0] = arr[size - 1];
        size--;
        heapify(0);
        return root;
    }

    // 최대값을 반환하는 함수
    public int getMax() {
        if (size <= 0) {
            System.out.println("Priority Queue is empty");
            return -1;
        }
        return arr[0];
    }
    }
```
##### 힙 기반 우선순위 큐
- 정의:
-- 힙을 사용하여 우선순위 큐를 구현.
- 특징:
-- 최소 힙(Min Heap)에서는 가장 작은 값이 루트에 오며, 최대 힙(Max Heap)에서는 가장 큰 값이 루트에 온다.
-- 힙을 이용한 우선순위 큐는 자기 정렬된 특성을 유지한다.
- 장점:
-- 효율적이다. 삽입과 삭제가 O(log n)의 시간 복잡도를 가지며, 매우 효율적이다.
-- 자동 정렬이 이루어지므로, 삽입과 삭제 후 우선순위가 자동으로 조정된다.
- 단점:
-- 구현이 복잡하다. 배열 기반 구현보다 구조가 복잡하고, 힙을 유지하는 과정에서 추가적인 작업이 필요하다.

## 덱(Deque)
- 정의: 
-- 양쪽 끝에서 요소를 삽입하고 삭제할 수 있는 큐.
- 특징:
-- 덱은 앞과 뒤 양쪽 끝에서 삽입과 삭제가 가능하다.
-- 덱은 큐의 FIFO 특성과 스택의 LIFO 특성을 모두 지원할 수 있다.
- 주요 연산: insertFront(), insertLast(), deleteFront(), deleteLast(), getFront(), getRear()

#### 배열 기반 덱(Array-based Deque)
- 특징:
-- 고정 크기 배열을 사용하여 구현되며, 덱의 크기가 배열의 크기에 의해 제한된다.
-- 원형 배열(Circular Array) 방식으로 구현될 수 있으며, 배열의 끝이 다 차면 처음으로 돌아가서 빈 공간을 재사용한다.

- 장점:
-- 배열을 사용하여 인덱스 기반으로 요소에 접근할 수 있어 O(1)의 시간 복잡도로 접근이 가능하다.
- 단점:
-- 배열 크기가 고정되어 덱이 꽉 차면 더 이상 요소를 삽입할 수 없고, 크기 조정이 필요하다. 크기 조정 시 O(n)의 시간 복잡도가 발생할 수 있다.

- 예시:
```c
//c에서의 Array-based Deque
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 5

typedef struct {
    int arr[MAX_SIZE];
    int front;
    int rear;
} Deque;

void initDeque(Deque* deque) {
    deque->front = -1;
    deque->rear = -1;
}

int isFull(Deque* deque) {
    return (deque->front == (deque->rear + 1) % MAX_SIZE);
}

int isEmpty(Deque* deque) {
    return (deque->front == -1);
}

void insertFront(Deque* deque, int value) {
    if (isFull(deque)) {
        printf("Deque is full\n");
        return;
    }

    if (isEmpty(deque)) {
        deque->front = 0;
        deque->rear = 0;
    } else {
        deque->front = (deque->front - 1 + MAX_SIZE) % MAX_SIZE;
    }
    deque->arr[deque->front] = value;
}

void insertRear(Deque* deque, int value) {
    if (isFull(deque)) {
        printf("Deque is full\n");
        return;
    }

    if (isEmpty(deque)) {
        deque->front = 0;
        deque->rear = 0;
    } else {
        deque->rear = (deque->rear + 1) % MAX_SIZE;
    }
    deque->arr[deque->rear] = value;
}

void deleteFront(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return;
    }

    if (deque->front == deque->rear) {
        deque->front = -1;
        deque->rear = -1;
    } else {
        deque->front = (deque->front + 1) % MAX_SIZE;
    }
}

void deleteRear(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return;
    }

    if (deque->front == deque->rear) {
        deque->front = -1;
        deque->rear = -1;
    } else {
        deque->rear = (deque->rear - 1 + MAX_SIZE) % MAX_SIZE;
    }
}

int getFront(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return -1;
    }
    return deque->arr[deque->front];
}

int getRear(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return -1;
    }
    return deque->arr[deque->rear];
}
```
```java
//Java에서의 Array-based Deque
public class ArrayDeque {
    private static final int MAX_SIZE = 5;
    private int[] arr;
    private int front, rear;

    public ArrayDeque() {
        arr = new int[MAX_SIZE];
        front = -1;
        rear = -1;
    }

    // 덱이 꽉 찼는지 확인
    private boolean isFull() {
        return (front == (rear + 1) % MAX_SIZE);
    }

    // 덱이 비었는지 확인
    private boolean isEmpty() {
        return (front == -1);
    }

    // 앞에 삽입
    public void insertFront(int value) {
        if (isFull()) {
            System.out.println("Deque is full");
            return;
        }

        if (isEmpty()) {
            front = 0;
            rear = 0;
        } else {
            front = (front - 1 + MAX_SIZE) % MAX_SIZE;
        }
        arr[front] = value;
    }

    // 뒤에 삽입
    public void insertRear(int value) {
        if (isFull()) {
            System.out.println("Deque is full");
            return;
        }

        if (isEmpty()) {
            front = 0;
            rear = 0;
        } else {
            rear = (rear + 1) % MAX_SIZE;
        }
        arr[rear] = value;
    }

    // 앞에서 삭제
    public void deleteFront() {
        if (isEmpty()) {
            System.out.println("Deque is empty");
            return;
        }

        if (front == rear) {
            front = -1;
            rear = -1;
        } else {
            front = (front + 1) % MAX_SIZE;
        }
    }

    // 뒤에서 삭제
    public void deleteRear() {
        if (isEmpty()) {
            System.out.println("Deque is empty");
            return;
        }

        if (front == rear) {
            front = -1;
            rear = -1;
        } else {
            rear = (rear - 1 + MAX_SIZE) % MAX_SIZE;
        }
    }
}
```
#### 연결 리스트 기반 덱(LinkedList-based Deque)
- 특징:
-- 동적 크기를 지원하며 덱의 크기가 변경될 때 크기를 재조정할 필요가 없다.

- 장점:
-- 덱의 크기가 동적으로 변경되므로 메모리 낭비가 없으며, 크기 조정이 필요하지 않다.
-- 배열처럼 연속된 메모리 공간을 요구하지 않기 때문에 메모리 관리가 효율적이다.
- 단점:
-- 각 노드가 포인터를 저장해야 하므로, 배열보다 더 많은 메모리를 사용한다.
-- 메모리 낭비가 발생할 수 있다.
- 예시:
```c
//c에서의 LinkedList-based Deque
// 노드 정의
typedef struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
} Node;

// 덱 구조체 정의
typedef struct Deque {
    Node* front;
    Node* rear;
} Deque;

// 덱 초기화
void initDeque(Deque* deque) {
    deque->front = NULL;
    deque->rear = NULL;
}

// 덱이 비었는지 확인
int isEmpty(Deque* deque) {
    return deque->front == NULL;
}

// 앞에 삽입
void insertFront(Deque* deque, int value) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = deque->front;
    newNode->prev = NULL;

    if (isEmpty(deque)) {
        deque->front = newNode;
        deque->rear = newNode;
    } else {
        deque->front->prev = newNode;
        deque->front = newNode;
    }
}

// 뒤에 삽입
void insertRear(Deque* deque, int value) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = deque->rear;

    if (isEmpty(deque)) {
        deque->front = newNode;
        deque->rear = newNode;
    } else {
        deque->rear->next = newNode;
        deque->rear = newNode;
    }
}

// 앞에서 삭제
void deleteFront(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return;
    }

    Node* temp = deque->front;
    deque->front = deque->front->next;

    if (deque->front == NULL) {
        deque->rear = NULL;
    } else {
        deque->front->prev = NULL;
    }
    
    free(temp);
}

// 뒤에서 삭제
void deleteRear(Deque* deque) {
    if (isEmpty(deque)) {
        printf("Deque is empty\n");
        return;
    }

    Node* temp = deque->rear;
    deque->rear = deque->rear->prev;

    if (deque->rear == NULL) {
        deque->front = NULL;
    } else {
        deque->rear->next = NULL;
    }

    free(temp);
}
```
```
//Java에서의 LinkedList-based Deque
public class LinkedListDeque {
    private static class Node {
        int data;
        Node next;
        Node prev;

        public Node(int data) {
            this.data = data;
            this.next = null;
            this.prev = null;
        }
    }

    private Node front;
    private Node rear;

    // 덱 초기화
    public LinkedListDeque() {
        front = null;
        rear = null;
    }

    // 덱이 비었는지 확인
    public boolean isEmpty() {
        return front == null;
    }

    // 앞에 삽입
    public void insertFront(int value) {
        Node newNode = new Node(value);
        if (isEmpty()) {
            front = newNode;
            rear = newNode;
        } else {
            newNode.next = front;
            front.prev = newNode;
            front = newNode;
        }
    }

    // 뒤에 삽입
    public void insertRear(int value) {
        Node newNode = new Node(value);
        if (isEmpty()) {
            front = newNode;
            rear = newNode;
        } else {
            newNode.prev = rear;
            rear.next = newNode;
            rear = newNode;
        }
    }

    // 앞에서 삭제
    public void deleteFront() {
        if (isEmpty()) {
            System.out.println("Deque is empty");
            return;
        }
        if (front == rear) {
            front = null;
            rear = null;
        } else {
            front = front.next;
            front.prev = null;
        }
    }

    // 뒤에서 삭제
    public void deleteRear() {
        if (isEmpty()) {
            System.out.println("Deque is empty");
            return;
        }
        if (front == rear) {
            front = null;
            rear = null;
        } else {
            rear = rear.prev;
            rear.next = null;
        }
    }
}
```
## Tree
- 정의: 
-- 노드와 노드를 연결하는 간선(edge)로 구성된 자료구조.
- 특징:
-- 계층적 구조로 1대N 의 관계를 표현
-- 순환이 없는 연결 그래프
-- 모든 노드는 단 하나의 부모를 가짐
-- 트리는 자기 자신을 포함하는 서브트리로 나눌 수 있음
- 주요 개념
-- 루트 노드: 트리의 최상단에 있는 노드
-- 자식 노드: 특정 노드와 연결된 하위 노드
-- 부모 노드: 자식 노드와 연결된 상위 노드
-- 형제 노드: 같은 부모를 공유하는 노드
-- 리프 노드: 자식이 없는 노드
-- 높이: 루트 노드에서 리프 노드까지의 경로 길이
-- 레벨: 루트 노드를 0으로 시작하여 깊이에 따라 증가하는 값
-- 차수: 노드가 가지는 자식의 수

#### 이진 트리(Binary Tree)
- 정의: 
-- 각 노드가 최대 두 개의 자식 노드를 가지는 트리 구조
- 특징:
--  각 노드는 최대 2개의 노드를 가진다.
-- 이진 트리는 자기 자신을 포함한 재귀적인 구조로 모든 서브트리 또한 이진트리이다.
![image](/image/이진트리.png)

##### 포화 이진 트리 (Full Binary Tree)
- 정의:
-- 모든 노드가 0개 또는 2개의 자식만을 가지는 트리.
- 특징:
-- 배열 크기가 고정되어 있어서 메모리 할당도 한 번만 이루어진다.
-- 트리의 모든 레벨이 노드로 꽉 차있음.
-- 모든 리프 노드가 동일한 깊이를 가짐.
- 장점:
-- 모든 레벨이 가득 차있어, 트리의 높이가 최소화되어 탐색, 삽입, 삭제에서 효율적인 연산을 가능함.
- 단점:
-- 모든 레벨이 가득 차 있어야 하므로 삽입/삭제 시 구조를 유지하려면 많은 재구성이 필요하다.
-- 노드의 데이터가 적을 경우, 트리의 크기가 고정되어 있어 비효율적인 메모리 사용을 초래함.
![image](/image/포화이진트리.png)

##### 완전 이진 트리(Complete binary tree)
- 정의:
-- 모든 노드가 0개 또는 2개의 자식만을 가지는 이진 트리.
- 특징:
-- 마지막 레벨(level)을 제외하고 모든 노드가 채워져있어야 한다.
-- 마지막 레벨의 노드는 다 채워져있을 수도 있고, 아닐수도 있다.
-- 모든 리프 노드가 동일한 깊이를 가짐.
- 장점:
-- 배열로 구현하면 부모와 자식 관계를 간단히 인덱스로 접근할 수 있다.
-- 완전 이진 트리의 높이가 작으므로, 탐색, 삽입, 삭제가 상대적으로 빠르다.
- 단점:
-- 배열로 구현할 경우, 노드가 비어 있으면 메모리 낭비가 발생할 수 있다.
-- 노드 삽입 시 완전성을 유지하기 위해 추가 작업이 필요하다.
![image](/image/완전이진트리.png)

##### 경사 트리 (Skewed Tree)
- 정의:
-- 모든 노드가 하나의 방향(왼쪽 또는 오른쪽)으로만 자식을 가지는 이진 트리.
- 특징:
-- 모든 레벨에서 노드가 하나만 존재하며 트리의 깊이가 최대가 되는 구조
-- 왼쪽 경사 트리, 오른쪽 경사 트리의 종류를 가짐.
-- N개의 노드를 가진 경사 트리의 높이는 항상 N이다.
- 장점:
-- 단순한 구조로 인해 구현이 상대적으로 쉽다.
- 단점:
-- 트리의 깊이가 깊어지면서 이진 트리의 장점을 상실한다.
-- 공간 복잡도가 증가하며, 균형 잡힌 트리보다 비효율적이다.

    ![image](/image/경사트리.jpg)

##### 수식 트리(Expression Tree)
- 수학적인 수식을 트리 구조로 표현
- 내부 노드는 연산자, 리프 노드는 피연산자를 나타내는 이진 트리 구조
- 후위 표기법, 중위 표기법을 사용하여 수식 트리 구성 가능

#### AVL 트리(Adelson-Velsky and Landis Tree)
- 삽입과 삭제 연산 후, 트리의 균형을 유지하기 위해 자동을 회전을 수행하는 트리.
- 이진 탐색 트리의 

#### 트리 순회
- 정의:
-- 트리 구조를 순차적으로 탐색하는 방법으로, 트리의 각 노드를 방문하는 순서를 정의한다.
- 특징:
-- 깊이 우선 탐색(DFS), 너비 우선 탐색(BFS)로 나뉜다.

##### 전위 순회(Pre-order Traversal)
- 정의:
-- 루트를 먼저 방문하고, 왼쪽 서브트리와 오른쪽 서브트리를 순차적으로 방문하는 방법.
- 특징:
-- 트리의 구조를 복제하거나 표현식을 구성할 때 유용.
- 장점:
-- 각 서브트리의 루트를 먼저 방문하므로, 노드의 계층적인 우선순위를 즉시 파악 가능.
-- 트리의 구조를 재구성하거나 저장할 때 유용.

- 단점:
-- 특정 데이터를 정렬하거나 후위 계산이 필요한 경우에는 부적합.
-- 트리의 계층 구조는 알 수 있지만 세부적인 순서는 확인이 어려움.
![image](/image/preorder.png)

##### 중위 순회(In-order Traversal)
- 정의:
-- 왼쪽 서브트리, 루트, 오른쪽 서브트리 순으로 방문하는 방법.
- 특징:
-- 이진 탐색 트리(BST)에서 중위 순회 결과는 항상 정렬된 순서를 보장.
-- 트리에서 정렬된 데이터를 얻는 데 적합.
- 장점:
-- 트리 탐색 중 정렬과 탐색 작업을 동시에 수행 가능.
- 단점:
-- 트리의 계층적 구조를 파악하기 어렵고, 단순 정렬 작업에만 적합.
-- 루트 노드의 우선적인 처리가 필요한 경우 부적합.

- 활용 방안:
-- 데이터베이스의 범위 질의(range query).
![image](/image/inorder.png)

##### 후위 순회(Post-order Traversal)
- 정의:
-- 왼쪽 서브트리, 오른쪽 서브트리, 그리고 루트 순으로 방문하는 방법.
- 특징:
-- 부모 노드를 처리하기 전에 모든 자식 노드의 작업이 완료된다.
-- 특정 노드를 빨리 찾고자 할 때는 비효율적.
- 장점:
-- 연속된 메모리 공간을 차지하기 때문에 접근 속도가 빠르다.
- 단점:
-- 루트를 마지막에 방문하므로 계층적 구조를 즉시 파악하기 어려움.
- 활용 방안:
-- 표현식 트리에서 계산(예: 3 + (4 * 5) 같은 수식을 계산).
-- 파일 및 디렉토리 삭제(부모를 지우기 전에 하위 파일과 폴더를 모두 삭제).
![image](/image/postorder.png)

##### 레벨 순회(Level-order Traversal)
- 정의:
-- 트리의 깊이(레벨) 순서대로 방문하는 방법.
- 특징:
-- 트리의 구조를 계층적으로 탐색 가능.
-- 너비 우선 방식이므로 최단 경로를 찾는 데 유리.
- 장점:
-- 계층적 구조를 직관적으로 탐색 가능.
-- 너비 우선 방식이므로 최단 경로 탐색에 적합.
- 단점:
-- 추가적인 메모리(큐)가 필요하며, 트리의 크기가 크면 큐의 크기가 급격히 증가.
-- 특정 노드의 정확한 위치를 알기 위해 모든 노드를 탐색해야 할 수 있음.
- 활용 방안:
-- 네트워크의 최단 경로 탐색.
-- 조직도나 계층 구조 분석.
![image](/image/levelorder.png)

#### 이진 탐색 트리(Binary Search Tree)
- 정의: 
-- 각 노드가 최대 두 개의 자식 노드를 가지고, 노드의 키 값이 특정 규칙을 따라 정렬되어 있는 트리.
- 특징:
-- 왼쪽 서브트리의 모든 노드 키 값은 현재 노드의 키 값보다 작음
-- 오른쪽 서브트리의 모든 노드 키 값은 현재 노드의 키 값보다 큼.
-- 트리를 중위 순회하면, 키 값이 오름차순으로 정렬된 결과를 얻을 수 있음.
-- 일반적으로 중복 키를 허용하지 않음(설계에 따라 달라질 수 있음).
- 장점:
-- 효율적인 탐색, 삽입, 삭제
-- 중위 순회를 통해 정렬된 데이터 획득 가능
- 단점:
-- 균형 유지의 어려움
-- 중복 값 처리 제한
- 활용 예시:
-- 데이터 검색, 삽입, 삭제가 빈번한 시스템.
-- 사전(dictionary)와 같은 정렬된 데이터를 다루는 경우.

##### 균형 이진 탐색 트리 (Balanced BST)
- 정의:
-- 이진 탐색 트리(BST)의 단점을 개선한 데이터 구조로, 트리의 높이를 균형 있게 유지하여 최악의 경우 성능 저하를 방지.
- 특징:
-- 균형 이진 탐색 트리의 주요 목표는 트리의 높이를 최소화하는 것

###### AVL 트리 (Adelson-Velsky and Landis Tree)
- 정의:
  이진 탐색 트리(BST)의 일종으로, 트리의 균형을 유지하기 위해 자가 균형 기능을 제공하는 자료 구조
- 특징:
  - 왼쪽, 오른쪽 서브 트리의 높이 차이가 최대 1이다.
그림에서 노드 위의 값은 BF(Balance Factor)로 서브트리의 높이 차이를 나타낸다.
  ![image](/image/AVLTree.png)
  - 어떤 시점에서 높이 차이가 1보다 커지면 회전(rotation)을 통해 균형을 잡아 높이 차이를 줄인다.
그림에서는 오른쪽으로 회전하여 균형을 맞추는 과정이다.
  ![image](/image/RRcase.png)
  - AVL 트리는 높이를 logN으로 유지하기 때문에 삽입, 검색, 삭제의 시간 복잡도는 O(logN)이다.
- 장점:
  - 검색, 삽입, 삭제 작업을 모두 O(log N) 시간에 처리할 수 있다.
  - 삽입 및 삭제 시 균형을 자동으로 맞추기 때문에 사용자가 별도로 균형을 맞출 필요가 없다.
  - 트리의 높이가 균형을 이루어 메모리 사용 효율이 높다.
- 단점:
  - 노드를 삽입하거나 삭제할 때, 트리가 균형을 잃으면 여러 번 회전을 수행해야 할 수 있어, 비용이 증가될 수 있다.
  - 균형을 조정하는 로직을 포함하므로, 구현이 복잡할 수 있다.
- 예시:
  - DB에서의 인덱스 구현으로 빠른 검색
  - 파일 시스템에서의 디렉토리 구조나 데이터를 관리할 때, 빠른 검색

###### 레드-블랙 트리 (Red-Black Tree)
- 정의:
  - 각 노드가 레드 또는 블랙 색상을 가지고 균형을 유지하며 삽입 및 삭제가 이루어지는 자가 균형 이진 트리
  ![image](/image/RVTree.jpg)

- 특징:
  - 각 노드는 레드 또는 블랙 색상을 가짐.
  - 루트 노드는 항상 블랙.
  - 레드 노드는 두 자식을 가질 수 없고, 레드 노드의 자식은 반드시 블랙이어야 함.
  - 모든 경로에서 루트에서 리프까지의 블랙 노드의 수가 동일.
  - 리프 노드는 가상의 블랙 노드로 간주.

- 장점:
  - 트리의 높이가 O(log N)로 유지되므로, 검색, 삽입, 삭제 연산이 효율적임.
  - AVL 트리보다 균형을 맞추는 과정이 간단하여 구현이 상대적으로 쉬움.
- 단점:
  - 입이나 삭제 시 불균형이 발생하면 회전 연산이 필요하여 추가적인 시간이 소요
  - AVL 트리에 비해 균형 조건이 덜 엄격하여 최악의 경우 성능이 떨어질 수 있음.
- 예시:
  - 메모리 관리 및 프로세스 스케줄링
  - C++의 Map
  - 자바의 TreeMap
###### Splay Tree
- 정의:
  - 특정 연산을 수행할 때마다 해당 노드를 트리의 루트로 이동시키는 특징을 가진 트리
- 특징:
  - 트리의 구조에 따라 zig, zig-zig, zig-zag의 총 3가지 방법이 존재한다.
    1. zig step: x가 parent가 있고 grandparent는 없을 때 rotate(x)한다.
    ![image](/image/zig.png)
    2. zig-zig step: x와 parent가 둘 다 left child거나 둘 다 right child면 rotate(parent)한 후 rotate(x)한다.
    ![image](/image/zig-zig.png)
    3. zig-zag step: x가 left child고 parent가 right child거나 그 반대의 경우 rotate(x)를 두 번 한다.
    ![image](/image/zig-zag.png)
- 장점:
  - 균형을 맞추는 과정이 상대적으로 단순하며, 트리의 회전 연산만으로 균형을 맞춘다.
  -  자주 접근되는 노드가 상위에 위치하게 되어, 자주 호출되는 작업에서 성능이 향상된다.
- 단점:
  - 스플레이 연산 후 트리의 구조가 자주 변화하여, 특정 작업에서 성능이 일정하지 않을 수 있다.
- 예시:
  - 캐시 시스템
  - 자주 접근되는 노드를 트리 상위에 배치하는 특성으로, 동적 집합 및 스택의 구현
  - 주로 삽입과 검색 연산이 반복되는 환경에서, 트리의 구조를 동적으로 최적화

##### B 트리 계열
###### B 트리 (B-Tree)
- 정의:
  -다항 탐색 트리의 일종으로, 모든 리프 노드가 같은 깊이에 위치하도록 균형을 맞추는 자가 균형 이진 검색 트리. 사진에서 리프 노드인 녹색 노드가 모두 깊이가 같다.
![image](/image/BTree.jpg)

- 특징:
  - 모든 리프 노드는 같은 깊이에 있다.
  - 내부 노드는 자식 노드의 개수를 여러 개 가질 수 있다 (2개 이상의 자식)
  - 각 노드는 최대 M개의 자식 노드를 가질 수 있으며, 최소 ⌈M/2⌉개의 자식 노드를 가질 수 있다.
  - 모든 노드는 키와 포인터를 저장하고, 키는 오름차순으로 정렬되어 있다.
  - 검색, 삽입, 삭제가 모두 O(log N) 시간 복잡도를 가진다.

- 장점:
  - 트리의 높이가 낮아 빠른 검색과 삽입/삭제 연산을 할 수 있다.
  - 자동으로 균형을 유지하므로 성능 저하가 없다.
- 단점:
  - 자식 노드 수가 다수일 수 있기 때문에 구현이 복잡할 수 있다.
  - 각 노드에 더 많은 자식 포인터를 저장해야 하므로 메모리 사용이 다소 많을 수 있다.
- 예시:
  - NTFS와 같은 파일 시스템에서 파일의 메타데이터 관리
  - DB의 인덱스 구조

###### B+ 트리 (B+ Tree)
- 정의:
  - B 트리의 변형으로, 모든 값이 리프 노드에만 저장되고, 내부 노드는 키 값만 저장하는 방식
리프 노드에만 AAA, BBB 등의 데이터가 존재한다.
![image](/image/Bplus.jpg)

- 특징:
  -  B 트리의 특성을 유지하면서, 모든 데이터가 리프 노드에만 집중되도록 설계되어, 범위 쿼리 및 순차 접근에 매우 효율적이다.
  -  리프 노드는 연결 리스트 형태로 연결되어 있어 순차 접근이 빠르다.
  -  B+ 트리의 리프 노드는 데이터를 저장하는 곳이며, 모든 검색 연산은 리프 노드에 도달한 후 데이터를 검색한다.
- 장점:
  - 리프 노드들이 연결되어 있어 범위 쿼리나 순차 접근이 매우 빠르다.
  - 데이터가 리프 노드에만 저장되므로 검색에 필요한 데이터 접근이 분리되어 효율적이다.
- 단점:
  - 삽입이나 삭제 시 리프 노드까지 영향을 미칠 수 있기 때문에 B 트리보다는 다소 복잡하고 시간이 걸릴 수 있다.
  - 모든 데이터가 리프 노드에 있기 때문에 중간 검색 단계가 상대적으로 간접적이다.

- 예시:
  - RDBMS에서의 인덱스 구축
  - 파일 시스템에서의 인덱스 구축
  - 검색 엔진에서의 인덱싱 시스템

###### B* 트리 (B* Tree)
- 정의:
  - B* 트리는 B 트리의 변형으로, 노드 분할이 일어날 때 두 개 이상의 자식 노드를 부모로 병합하는 방식
- 특징:
  - 노드 분할 시, 하나의 자식 노드가 아닌 두 개 이상의 자식 노드를 부모로 병합하여 효과적으로 균형을 유지.
  - 리프 노드는 B+ 트리처럼 데이터만 저장.
  - 내부 노드는 부모 노드와 자식 노드 사이에 값을 분배하여 균형을 유지.
  - 트리의 노드가 꽉 찼을 때, 분할 대신 자식 노드들끼리 합병하여 트리 구조를 조정.
- 장점:
  - B 트리보다 트리가 더 넓고 낮아서 디스크 I/O가 더 효율적이다.
  - 노드가 꽉 차면 단순히 분할하지 않고 병합하므로, 트리가 더욱 균형 있게 유지된다.
- 단점:
  - 노드 분할 방식과 병합 과정이 복잡하여 구현이 어려울 수 있다.
  - 병합이 자주 일어나기 때문에 더 많은 메모리 자원을 소비할 수 있다.
- 예시:
  - B 트리보다 고급 데이터베이스 시스템에서 사용
  - ZFS와 같은 고급 파일 시스템
  - 실시간 데이터 처리 시스템

#### 힙
- 정의: 
  - 완전 이진 트리의 일종으로, 특정한 우선순위에 따라 데이터를 저장하는 자료구조.
- 특징:
  - 모든 부모 노드가 자식 노드보다 우선순위가 높은 특성을 가짐.

![image](/image/heap.png)
##### 최대 힙(Max Heap)
- 정의:
  - 부모 노드의 값이 자식 노드의 값보다 크거나 같은 트리 구조
- 특징:
  - 부모 노드의 값이 자식 노드의 값보다 크거나 같은 성질.
  - 루트 노드가 가장 큰 값을 가지고, 모든 부모 노드는 자식보다 크거나 같다.
- 장점:
  - 연속된 메모리 공간을 차지하기 때문에 접근 속도가 빠르다.
- 단점:
  - 배열의 크기를 변경할 수 없기 때문에 유동적인 크기 조정이 불가능하다.
  - 메모리 낭비가 발생할 수 있다.
- 예시:
  - Priority Queue 구현으로 작업 스케쥴링, 네트워크 패킷 처리 등에서 사용
  - 데이터의 내림차순 정렬 수행 -> 상위 N개 데이터 추출 가능
  
##### 최소 힙(Min Heap)
- 정의:
  - 부모 노드의 값이 자식 노드의 값보다 크거나 같은 트리 구조
- 특징:
  - 부모 노드의 값이 자식 노드의 값보다 작거나 같은 성질.
  - 루트 노드가 가장 작은 값을 가지고, 모든 부모 노드는 자식보다 작거나 같다.
- 장점:
  - 연속된 메모리 공간을 차지하기 때문에 접근 속도가 빠르다.
- 단점:
  - 배열의 크기를 변경할 수 없기 때문에 유동적인 크기 조정이 불가능하다.
  - 메모리 낭비가 발생할 수 있다.
- 예시:
  -  네비게이션의 최단 경로 찾기
  -  데이터의 올림차순 정렬 수행 -> 하위 N개 데이터 추출 가능

##### 피보나치 힙 (Fibonacci Heap)
- 정의:
  - 피보나치 힙은 여러 개의 리스트 형태의 트리를 이용하여 데이터를 저장하는 힙 자료구조이다.
- 특징:
  - 피보나치 힙은 각 트리가 피보나치 수열의 크기를 기반으로 결합되며, 이로 인해 트리의 크기를 일정하게 유지할 수 있다. 
  - 피보나치 힙은 최소 힙(Min Heap)의 특성을 가짐.
  - 피보나치 힙의 각 트리는 서로 연결되어 있고, 연결은 느슨하게 이루어지며 삽입과 삭제 연산이 빠르게 수행된다.
  - 피보나치 힙은 연산을 지연(Lazy)시키는 방식으로 작업을 처리한다. 예를 들어, 트리를 병합할 때는 그 즉시 트리를 병합하지 않고, 나중에 필요할 때 병합을 수행한다.
- 장점:
  - 삽입과 병합의 연산이 매우 빠름.
  - 연산 지연으로 불필요한 작업을 줄임.
- 단점:
  - 구현이 복잡함.
  - 트리 구조가 느슨하여 메모리 사용량이 많다.
- 예시:
  -  작업의 스케쥴링으로 우선순위에 맞추어 작업 처리
  -  MST를 구할 때, 최솟값 추출이 효율적임.

#### 분리 집합(Disjoint Set)
- 정의: 
  - 서로 중복되지 않은 부분 집합들로 나누어진 원소들에 대한 정보를 저장하고 조작하는 자료 구조.
- 특징:
  - 가장 효율적인 트리 구조로 집합을 구현.
- 주요 연산:
  - 찾기(Find), 합집합(Union)

##### Union-Find 알고리즘
- 정의:
  - 분리 집합을 구현하고 조작하는 자료 구조의 알고리즘.
- 특징:
  - 분리 집합을 합치는 union 연산과 임의의 원소가 어떤 집합에 속하는 지 찾는 find 연산을 제공
  - Tree 구조로 집합을 표현하고, 각 원소는 자신을 대표하는 루트를 가리킨다.
  - Find 연산을 최적화하는 방법으로, 트리의 경로를 압축하여 이후 찾기 연산을 더 빠르게 만든다.
  - Union 연산 시 트리의 깊이를 최소화하기 위해, 작은 트리를 큰 트리로 합친다.

- 수행 방식:
![image](/image/unionfind.png)
  - node는 4개이고, parent[node]는 node의 부모 노드 번호이다.
  - 각 step에서 union(a,b)연산을 통해 a,b 노드를 연결한다.
- 장점:
  - Find와 Union 연산이 상수 시간에 가까운 시간 복잡도를 가지므로, 대규모 데이터에 대해서도 매우 효율적이다.
  - 구현이 단순하다.
  - 집합 간 연결 여부를 추척하기에 빠름.
- 단점:
  - 원소 순서의 변경이 어려움.
  - 동적 연결성과 같은 특정 문제에서만 유용하다.
- 예시:
  -  블록체인에서의 트랜잭션 간의 관계 추적
  -  서버 간의 연결 상태를 추적하거나, 두 네트워크의 연결 여부를 확인.
  -  무방향 그래프에서 사이클을 탐지
  

##### 경로 압축 및 크기 조정(Path Compression and Union by Size)
- 정의:
  - Union-Find 알고리즘에서 효율성을 극대화하는 두 가지 주요 기법이다.

- 특징:
  - 분리 집합을 합치는 union 연산과 임의의 원소가 어떤 집합에 속하는 지 찾는 find 연산을 제공
  - Tree 구조로 집합을 표현하고, 각 원소는 자신을 대표하는 루트를 가리킨다.
  - Find 연산을 최적화하는 방법으로, 트리의 경로를 압축하여 이후 찾기 연산을 더 빠르게 만든다.
  - Union 연산 시 트리의 깊이를 최소화하기 위해, 작은 트리를 큰 트리로 합친다.
  - 두 방법을 결합한 분리 집합은 상수시간에 가까운 성능 제공.

- 경로압축(Path Compression)
![image](/image/pathcompression.png)
- 정의:
  - Find 연산을 할 때마다 트리의 구조를 평평하게 만드는 방법.

- 특징:
  - 주어진 원소가 속한 집합의 대표자를 찾는 과정으로, 트리의 높이를 최소화하고 Find 연산을 수행할 때 트리의 경로에 있는 모든 노드를 대표자와 바로 연결.


- 크기 조정(Union by Size)
![image](/image/unionbysize.png)
- 정의:
  - 두 집합을 합칠 때, 트리의 크기를 고려하여, 작은 트리를 큰 트리에 합치는 방식.
- 특징:
  - 각 집합의 루트에 크기 정보를 저장하여, 크기를 비교한다.
  - 위의 사진에서 Union 연산 시에 크기가 큰 집합으로 합친다.


## Graph
- 정의:
  - 정점(Vertex, Node)과 정점을 연결하는 간선(Edge)로 구성된 자료구조.
  - 여러 개체들 간의 관계나 연결을 나타낼 때 사용.

- 특징:
  - 정점과 간선을 통해 데이터의 관계를 표현하므로, 관계형 데이터를 다루는 데 적합.

#### 그래프 종류

##### 방향 그래프(Digital Graph)
- 정의:
  - 각 간선이 특정 방향성을 가지는 그래프.
![image](/image/directedgraph.png)

- 특징:
  - 간선의 방향에 따라 그래프의 구조와 연결 관계가 달라짐.
  - 노드의 관계는 일방적일 수 있음.
- 장점:
  - 관계의 방향을 명확히 표현할 수 있음(예: 웹페이지 링크, 프로세스 흐름).
- 단점:
  - 복잡한 방향성으로 인해 분석 및 시각화가 어려울 수 있음.
- 예시:
  - 웹페이지의 하이퍼링크 구조.
  - 소셜 네트워크에서 팔로우 관계.

##### 무방향 그래프(Undirected Graph)
- 정의:
  - 각 간선이 방향성을 가지지 않는 그래프.
![image](/image/undirectedgraph.png)
- 특징:
  - 노드의 관계가 대칭적임.
  - 방향 정보가 없어 단순함.
  - 출발지와 도착지를 구분하지 않음.
  - 차수는 특정 정점에 연결된 간선의 수
- 장점:
  - 데이터 구조와 알고리즘이 단순함.
- 단점:
  - 방향성이 필요한 경우 비효율적임.
- 예시:
  - 도로 네트워크(양방향 도로).
  - 전기 회로의 연결 구조.

##### 가중 그래프(Weighted Graph)
- 정의:
  - 각 간선에 가중치(weight)가 부여된 그래프
![image](/image/weigraph.png)
- 특징:
  - 간선의 비용, 길이 등을 나타냄
- 장점:
  - 현실 세계의 다양한 상황을 모델링 가능
  - 최단 경로, 최소 비용 경로 등 계산 가능
- 단점:
  - 가중치 설정이 어렵거나 주관적임.
  - 계산 복잡도의 증가
- 예시:
  - GPS 내비게이션의 경로 탐색
  - 네트워크 데이터 전송에섯의 대역폭 계산

##### 비가중 그래프(Unweighted Graph)
- 정의:
  - 간선에 가중치가 없는 그래프
![image](/image/weigraph.png)

- 특징:
  - 단순히 연결 관계만 나타냄
  - 모든 간선의 중요도가 동일한 것으로 간주됨.
- 장점:
  - 데이터 처리와 알고리즘 구현이 간단함.
  - 가중치 설정이 없어서 직관적임.
- 단점:
  - 가중치가 필요한 상황에서는 정보 손실 가능
- 예시:
  - SNS에서 단순 연결 여부 확인
  - 그래프의 기본 구조 분석

##### 완전 그래프(Complete Graph)
- 정의:
  - 모든 정점이 서로 연결된 그래프
![image](/image/completegraph.png)

- 특징:
  - 모든 정점 쌍 사이에 간선이 존재함.
  - 간선 수가 많아 밀도가 매우 높음.
- 장점:
  - 노드 간의 관계를 완벽히 표현
  - 연결성 분석에 유리함.
- 단점:
  - 간선의 수가 많아질 수록 저장공간과 계산 복잡도 증가
  - 대규모 네트워크에서는 비효율적
- 예시:
  - 소규모 네트워크의 전수조사
  - 네트워크의 모든 가능 경로 시뮬레이션

#### 그래프 표현 방식

##### 인접 행렬 (Adjacency Matrix)

- 정의:
  - 그래프의 연결 관계를 표현하기 위해 𝑛 × 𝑛 크기의 2차원 배열(행렬)로 나타내는 방식. 그림에서 행에는 출발지, 열에는 도착지가 나타나 있다. 
![image](/image/adjmatrix.png) 
- 특징:
  - 행렬의 요소는 두 노드 사이의 간선 유무나 가중치를 나타냄.
  - 밀도가 높은 그래프에 적합함.
- 구현 방식:
  - 인접 행렬을 adj[i][j]이라 할 때, i와 j 사이에 간선이 존재하며 1, 아니면 0
- 장점:
  - 노드 간의 간선 유무를 빠르게 확인 가능
  - 구현이 간단하고, 특정 알고리즘에서 활용이 용이함.
- 단점:
  - 연결된 노드를 찾기 위한 시간이 오래 걸림
- 예시:
  - 네트워크 플로우, 최단 경로 알고리즘에서 주로 사용

##### 인접 리스트 (Adjacency List)
- 정의:
  - 그래프와의 연결 관계를 vector의 배열로 나타내는 방식.
![image](/image/adjlist.png) 
- 특징:
  - 메모리 사용량: 𝑂(𝑉+𝐸), 𝑉는 노드, 𝐸는 간선의 개수.
  - 희소 그래프에 적합하다.
- 구현 방식:
  - list[𝑖]에 노드 𝑖와 연결된 노드들의 리스트를 저장한다.
- 장점:
  - 실제 노드의 개수에 비례하는 메모리만 차지한다.
  - 각 노드에 연결된 모든 노드를 탐색에 이점을 가짐.
- 단점:
  - 두 노드의 연결 여부를 확인하는 시간이 매우 오래걸린다.
- 예시:
  - 도로 네트워크, 소셜 네트워크에서 주로 사용

#### 그래프 순회
- 정의:
  - 하나의 정점으로부터 시작하여 차례대로 모든 정점을 한 번씩 방문하는 것

##### 너비 우선 탐색(Breath-First Search, BFS)
- 정의:
  - 한 정점에서 시작하여 인접한 정점들을 먼저 방문한 후, 정점들의 인접 정점들을 탐색하는 방법.
- 특징:
  - 재귀적으로 동작하지 않는다.
  - 어떤 노드를 방문했는 지 여부를 반드시 검사해야 한다.

- 동작 방식:
![image](/image/bfs-example.png) 
    1. 0 노드를 방문한다. -> 큐에 0 노드 삽입, 이후 a와 인접한 모두 노드 방문
    2. 큐에서 꺼낸 노드와 인접한 노드 모두 방문한다 -> 1, 2, 4 노드 방문
    3. 이후 1과 인접한 0,2 노드, 2와 인접한 1,3,4 노드, 4와 인접한 0, 3, 2 노드 방문
    4. 방문한 노드는 재방문 하지 않으므로 방문 순서는 0,1,2,4,3이 된다.
- 장점:
  - 너비를 우선으로 탐색하므로, 답이 여러 개여도 최단 경로임을 보장
  - 최단 경로를 반드시 찾을 수 있음
- 단점:
  - 노드의 수가 많을 수록, 큐에 많은 공간이 필요함
  - 노드의 수가 많아지면, 탐색해야 하는 노드의 수가 많아져 비효율적임.
- 예시:
  - 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때


##### 깊이 우선 탐색(Depth-First Search, DFS)
- 정의:
  - 루트 노드에서 시작해서, 자식의 노드들을 순서대로 탐색하는 방법.
- 특징:
  - 스택을 사용하여 구현하거나 재귀 호출을 통해 구현
  - 경로가 존재하면 해당 경로를 따라 끝까지 탐색하고, 갈 곳이 없으면 뒤로 돌아가며 다른 경로 탐색.

- 동작 방식:
![image](/image/dfs-example.png) 
    1. 0 노드를 방문한다. -> 큐에 0 노드 삽입, 이후 a와 인접한 모두 노드 방문
    2. 큐에서 꺼낸 노드와 인접한 노드 모두 방문한다 -> 1, 2, 4 노드 방문
    3. 이후 1과 인접한 0,2 노드, 2와 인접한 1,3,4 노드, 4와 인접한 0, 3, 2 노드 방문
    4. 방문한 노드는 재방문 하지 않으므로 방문 순서는 0,1,2,4,3이 된다.
- 장점:
  - 구현이 간단하다.
  - 찾아야 하는 노드가 깊은 단계에 있을 수록, 그 노드가 좌측에 있을 수록 BFS보다 유리하다.
- 단점:
  - 답이 아닌 경로가 매우 깊을 때, 시간이 오래 걸릴 수 있다.
- 예시:
  - 전자 회로에서 특정 단자끼리 연결되어 있는 지


#### 최단 경로 알고리즘
- 정의:
  - 두 노드 사이의 가장 짧은 경로를 찾는 알고리즘
- 특징:
  - 간선에 가중치가 부여된다.
##### 다익스트라 알고리즘 (Dijkstra's Algorithm)
- 정의:
  - 가중치가 있는 그래프에서 시작 정점부터 다른 모든 정점까지의 최단 경로를 찾는 알고리즘.
- 특징:
  - 단일 시작점에서 다른 모든 노드까지의 최단 경로를 찾음.
  - 간선의 가중치는 음수를 허용하지 않음
  - 실시간 최단 경로 탐색 상황에 적합하다.
- 동작 방식:
    1. 출발 노드를 설정한다.
    2. 최단 거리 테이블을 초기화 한다.
    3. 방문하지 않은 노드 중 가장 짧은 노드를 선택한다.
    4. 해당 노드를 거쳐 이동하는 비용 게산하여 테이블 갱신.
- 장점:
  - 구현이 단순하다.
  - 효율적인 경로 탐색이 가능.
- 단점:
  - 모든 가중치가 양수일 때만 작동한다.
  - 대규모 네트워크에서는 계산 시간이 길어짐.
- 예시:
  - GPS 네비게이션 시스템의 최적 경로 제공
  - 물류 시스템의 화물 운송 최적의 경로 제공

##### 벨만-포드 알고리즘 (Bellman-Ford Algorithm)
- 정의:
  - 다익스트라와 유사하지만, 음수 가중치가 있을 경우에도 사용할 수 있는 알고리즘.
- 특징:
  - 단일 출발점 최단 경로 문제를 해결
  - 브루트 포스 전략을 사용한다.
- 동작 방식:
![image](/image/bellman.png) 
    1. 출발 노드 설정
    2. 최단 거리 테이블을 초기화
    3. 모든 간선에 대해 각 간선을 거쳐 다른 노드로 가는 비용을 계산하여, 테이블을 갱신 -> N-1 번 반복
- 장점:
  - 음수 가중치에서도 사용 가능하다.
- 단점:
  - 다익스트라 알고리즘에 비해 느리지만 
- 예시:
  - 환율 차익 거래 방지 시스템
  - 다양한 비용 구조를 가지는 로봇의 경로 최적화

##### 플로이드-워셜 알고리즘 (Floyd-Warshall Algorithm)
- 정의:
  - 그래프에서 모든 노드 간의 최단 경로를 구하는 알고리즘
- 특징:
  - 모든 노드에서 다른 모든 노드까지의 최단 경로 계산
  - 음의 가중치가 있는 간선에서도 사용 가능
  - 2차원 배열을 사용해 최단 거리 정보 저장
- 동작 방식:
![image](/image/bellman.png) 
    1. 모든 노드 쌍에 대해 직접 연결된 경로의 거리를 2차원 배열에 저장.
    2. 각 노드를 중간 경유지로 고려하여 경로 갱신
    3. D[S][E] = Math.min(D[S][E], D[S][K] + D[K][E])의 점화식으로 경로 계산.
    D[S][E]는 노드 S에서 노드 E까지의 최단 거리를 저장하는 배열이다.
- 장점:
  - 모든 노드 쌍 간의 최단 경로를 한 번에 계산할 수 있다.
  - 구현이 간단함.
- 단점:
  - 시간 복잡도가 높아 대규모 그래프에서는 비효율적임.
- 예시:
  - 도시 간 최단 경로 계산
  - 항공사의 최적 비행 경로 설계
#### 최소 신장 트리 (Minimum Spanning Tree)
- 정의:
  - 가중치가 있는 연결 그래프에서 모든 정점을 연결하는 간선들의 합이 최소가 되는 트리를 찾는 알고리즘.
- 특징:
  - n개의 정점을 가진 그래프는 n-1개의 간선을 가진다.
  - 하나의 그래프에 여러 개의 최소 신장 트리가 존재한다.
  - 양방향 가중 그래프에서 정의된다.
  - 사이클이 생기지 않는다.

##### 크루스칼 알고리즘 (Kruskal's Algorithm)
- 정의:
  - 간선의 가중치가 작은 순으로 간선을 추가해 가며 최소 신장 트리를 찾는 알고리즘.
- 특징:

- 동작 방식:
    1. 그래프의 모든 간선을 가중치 기준으로 오름차순 정렬한다.
    2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택한다.
    3. 선택된 간선을 현재의 MST 집합에 추가한다.
    4. 모든 정점이 연결될 때까지 2~3 과정을 반복한다.

- 장점:
  - 구현이 간단함.
  - 메모리 사용이 효율적임.
- 단점:
  - 간선이 많은 밀집 그래프에서는 정렬에 시간이 오래 걸림.
- 예시:
  - 네트워크 설계

##### 프림 알고리즘 (Prim's Algorithm)
- 정의:
  - 시작 정점에서부터 트리를 확장해 가면서 최소 신장 트리를 찾는 알고리즘
- 특징:
  - 정점을 중심으로 MST를 만들어 나간다.
- 동작 방식:
    1. 임의의 간선을 하나 선택한다.
    2. 선택한 간선의 정점과 인접한 정점 중에서, 최소 가중치의 간선으로 연결된 정점과 연결 
    3. 모든 정점이 선택되면 완료.
- 장점:
  - 간선이 많은 그래프에서 효율적이다.
  - 시작 정점을 선택할 수 있어, MST 구성에 유리하다.
- 단점:
  - 우선순위 큐를 사용하므로, 구현이 복잡핟.
- 예시:
  - 대규모 네트워크 라우팅
- 
  

#### 위상 정렬 (Topological Sorting)
- 정의:
  - DAG(Directed Acyclic Graph)에만 적용 가능한 알고리즘으로, 정점들을 선형적으로 정렬하는 알고리즘.
- 특징:
  - 그래프의 각 간선이 정점 간의 순서를 지켜야 한다는 조건을 만족해야 함.
  - 하나의 그래프에서 여러 가지 결과가 가능하다.
- 동작 방식:
    1. 진입 차수가 0인 모든 정점을 큐에 삽입한다.
    2. 큐에서 원소를 꺼내 해당 정점과 연결된 간선을 제거한다.
    3. 간선 제거 후 진입 차수가 0이 된 정점을 큐에 삽입한다.
    4. 큐가 빌 때까지 2-3 과정을 반복한다.

- 장점:
  - 복잡한 작업의 순서를 단순화한다.
  - 사이클 존재 여부를 확인할 수 있다.
- 단점:
  - DAG에만 사용 가능하므로, 적용 범위가 제한적임
  - 여러 가지 결과가 가능하여, 유일한 해를 구하기 어려움.
- 예시:
  - 프로젝트 일정 관리
  - 작업 스케쥴링
- 

#### 강결합 요소 탐색 (Strongly Connected Components)
- 정의:
  - 방향 그래프에서 모든 정점이 서로 도달 가능한 정점들의 집합을 찾는 알고리즘.
- 특징:
  - 방향 그래프에서만 적용 가능
  - 하나의 강결합 요소 내에서는 모든 정점이 서로 도달가능하다.
  - DAG에서 사용한다.
- 장점:
  - 그래프의 구조를 단순하고 이해하기 쉽게 분해 가능
  - 대규모 그래프에서 효율적으로 작동
- 단점:
  - 구현이 복잡하다.
- 예시:
  - SNS에서의 사용자들 간의 관계 분석
  - 교통 네트워크 분석
- 
#### 이분 그래프 탐색 (Bipartite Graph Check)
- 정의:
  - 주어진 그래프가 이분 그래프인지 확인하는 과정
- 특징:
  - 주로 DFS나 BFS를 사용하여 계산한다.
  - 홀수 길이의 사이클이 존재하면, 이분 그래프가 될 수 없다.
- 장점:
  - 그래프 탐색이 효율적이다.
  - 복잡한 관계를 두 그룹으로 나누어 분석하여 다양한 문제 해결 가능
- 단점:
  - 제한된 그래프 구조
  - 복잡한 구현
- 예시:
  - 사용자와 제품 간의 관계를 모델링한 개인화된 추천 시스템
  - 직원-작업, 학생-강좌 등 최적의 매칭 찾기에 할용
- 

## 해시(Hash)
- 정의: 
  - 데이터를 입력받아 고정된 크기의 해시 값(Hash Value)을 생성하는 함수인 해시 함수(Hash Function)에 의해 수행됨.
- 특징:
  - 고정된 입출력 크기
  - 빠른 연산 속도
  - 동일 입력, 동일 출력
  - 서로 다른 입력값이 같은 해시 값을 가질 경우가 존재한다.
- 활용 사례:
  - 데이터 저장 및 검색(해시 테이블)
  - 데이터 무결성 확인
  - 비밀번호 저장 ->해시값으로 비밀번호 변경하여 저장
  - 블록체인에서 블럭 간 연결

#### 해시 테이블(Hash Table)
- 정의: 
  - 해시 함수로 변환한 값을 색인(index)으로 삼아 Key,Value를 저장하는 자료구조. 
![image](/image/hashtable.png) 

- 특징:
  - 검색, 삽입, 삭제가 매우 빠름

- 활용 사례:
  - 
#### 해시 함수 (Hash Function)
- 정의: 
  - 데이터를 입력받아 고정된 크기의 해시 값(Hash Value)을 생성하는 함수인 해시 함수(Hash Function)에 의해 수행됨.
- 특징:
  - 고정된 입출력 크기
  - 해시값을 통해 원래의 입력값을 추적하는 것은 매우 어렵거나 불가능
  - 입력값이 조금만 변경되어도 해시값이 크게 달라짐

- 활용 사례:
  - 데이터 무결성 검사
  - 디지털 서명 인증
  - 로드 밸런싱

#### 충돌 처리 (Collision Handling)
- 정의: 
  - 해시 테이블에서 서로 다른 두 개 이상의 키가 동일한 해시 값(버킷)을 가질 때 발생하는 문제를 해결하기 위한 방법
##### 개방 주소법 (Open Addressing)
- 정의:
  - 충돌이 발생했을 때, 데이터를 저장할 새 버킷을 해시 테이블 내부에서 탐색하여 저장하는 방식.
![image](/image/adjlist.png) 
- 특징:
  - 하나의 버킷에는 하나의 값만 저장할 수 있음.
- 구현 방식:
  1. 해시 테이블 배열 생성.
  2. 데이터 삽입 시, 해시 함수로 기본 위치 찾음, 충돌 시 빈 버킷 탐사하여 삽입
  3. 데이터 탐색 시, 충돌 처리 규칙에 따라 탐색하며 데이터 확인
- 장점:
  - 추가적인 자료구조가 필요 없음.
  - 데이터 접근 속도가 빠름.
- 단점:
  - 충돌 데이터가 한 곳에 몰릴 경우 탐색 효율성 저하
  - 테이블의 크기가 제한적이고, 재해싱이 필요할 수 있음.
- 예시:
  - 제한된 메모리 공간에서의 데이터 관리 시(캐시)
##### 체이닝 (Chaining)
- 정의:
  - 충돌이 발생했을 때, 동일한 해시 값을 가지는 데이터를 하나의 리스트에 저장하는 방식.
- 구현 방식:
  1. 해시 테이블 배열 생성.
  2. 데이터 삽입 시, 해시 함수로 기본 위치 찾음, 해당 버킷의 연결 리스트에 데이터 삽입
  3. 데이터 탐색 시, 연결리스트를 순회하며 확인
- 장점:
  - 충돌로 인해 데이터 손실이 발생하지 않음.
  - 해시 테이블 크기에 제약 없이 데이터를 저장 가능.
  - 충돌이 잦더라도 데이터 삽입과 탐색 성능이 일정.
- 단점:
  - 연결 리스트를 사용하므로 메모리 오버헤드가 발생.
  - 리스트가 길어지면 탐색 성능이 저하될 수 있음.
- 예시:
  - 데이터베이스 인덱스, 중복 키가 많은 경우
  - 충돌이 잦은 환경에서 데이터 관리
#### 동적 크기 조정 (Dynamic Resizing)
- 정의:
  - 데이터 구조(예: 배열, 해시 테이블 등)의 크기를 사용 중 동적으로 조정하여 공간 효율성과 성능을 극대화하는 기술
- 특징: 
  - 데이터 구조의 초기 크기가 제한적일 때, 데이터가 초과되거나 불필요하게 공간을 차지할 경우 크기를 늘리거나 줄이는 방식으로 활용

- 구현 방식:
  1. 기존 데이터 구조 크기 확인
  2. 새로운 크기 설정, 크기를 늘릴 때는 2배, 줄일 때는 1/2배 감소
  3. 데이터 재배치
  4. 참조 업데이트
- 장점:
  - 데이터가 증가하거나 감소해도 적응적으로 크기를 조정하여 유연한 메모리 관리가 가능.
  - 불필요한 메모리 낭비를 방지.
- 단점:
  - 크기 변경 시 데이터 복사가 필요하므로 𝑂(𝑛)시간 비용이 발생.
  - 동적 크기 조정을 설계하고 관리하는 코드가 복잡.
- 예시:
  - Python의 리스트, Java의 ArrayList.
  - 충돌이 잦은 환경에서 데이터 관리
#### 블룸 필터 (Bloom Filter)
- 정의:
  - 확률적 데이터 구조로, 주어진 집합에 특정 원소가 포함되어 있는지 빠르고 공간 효율적으로 판별할 수 있는 방식
- 특징:
  - 정확한 존재 여부를 판단하는 것이 아닌, 실제로 포함되지 않은 원소를 속한다고 판별하는 경우가 발생할 수 있음.
- 구현 방식:
  1. 해시 함수는 입력 값을 특정 위치 비트 배열에 매핑.
  2. 블룸 필터의 모든 비트를 0으로 설정
  3. 새로운 원소를 집합에 추가할 때, 그 원소를 여러 해시 함수에 입력하여 나온 값을 이용해 비트 배열의 특정 위치를 1로 설정.
- 장점:
  - 대량의 데이터를 처리하면서도 메모리 사용을 최소화할 수 있음.
  - 삽입 및 검색 시간이 매우 빠르며, 수백만 개의 원소를 다룰 때도 매우 효율적임.
  - 구현이 간단하고, 사용이 직관적입니다.
- 단점:
  - 거짓 긍정
  - 한 번 추가된 원소는 삭제 불가능.
- 예시:
  - 웹 페이지에서의 크롤링, 스팸 필터링
  - NoSQL DB에서 데이터를 빨리 찾기 위해 사용

