---
title: "Lecture 02 - 栈和队列"
date: "2026-06-17"
category: "数据结构"
  - 王道《数据结构》
  - 408历年真题
  - 《数据结构》严蔚敏
difficulty: 基础
---

## 1. 栈的定义

### 1.1 栈的基本概念

<span style="background-color:#ccc1d9">**栈**</span>是只允许在一端进行插入或删除操作的线性表。

- **栈顶**：允许插入和删除的一端
- **栈底**：不允许插入和删除的一端
- **空栈**：不含任何元素的栈

<span style="background-color:#8db3e2">**栈的特性**：后进先出（Last In First Out，LIFO）</span>

### 1.2 栈的基本操作

| 操作 | 描述 |
|------|------|
| `InitStack(&S)` | 初始化栈 |
| `DestroyStack(&S)` | 销毁栈 |
| `Push(&S, x)` | 进栈，元素 $x$ 入栈 |
| `Pop(&S, &x)` | 出栈，栈顶元素出栈，用 $x$ 返回 |
| `GetTop(S, &x)` | 读栈顶元素 |
| `StackEmpty(S)` | 判断栈是否为空 |

---

## 2. 顺序栈

### 2.1 顺序栈的定义

```c
#define MaxSize 100
typedef struct {
    ElemType data[MaxSize];
    int top;
} SqStack;
```

**初始化**：`S.top = -1`，表示空栈

### 2.2 顺序栈的基本操作

#### 2.2.1 进栈操作

```c
bool Push(SqStack &S, ElemType x) {
    if (S.top == MaxSize - 1) return false;
    S.data[++S.top] = x;
    return true;
}
```

#### 2.2.2 出栈操作

```c
bool Pop(SqStack &S, ElemType &x) {
    if (S.top == -1) return false;
    x = S.data[S.top--];
    return true;
}
```

#### 2.2.3 读栈顶元素

```c
bool GetTop(SqStack S, ElemType &x) {
    if (S.top == -1) return false;
    x = S.data[S.top];
    return true;
}
```

---

## 3. 链栈

### 3.1 链栈的定义

```c
typedef struct LinkNode {
    ElemType data;
    struct LinkNode *next;
} *LinkStack;
```

### 3.2 链栈的进栈操作

```c
bool Push(LinkStack &S, ElemType x) {
    LinkNode *s = (LinkNode*)malloc(sizeof(LinkNode));
    s->data = x;
    s->next = S;
    S = s;
    return true;
}
```

### 3.3 链栈的出栈操作

```c
bool Pop(LinkStack &S, ElemType &x) {
    if (S == NULL) return false;
    LinkNode *p = S;
    x = p->data;
    S = S->next;
    free(p);
    return true;
}
```

---

## 4. 队列的定义

### 4.1 队列的基本概念

<span style="background-color:#ccc1d9">**队列**</span>是只允许在一端进行插入，另一端进行删除的线性表。

- **队头**：允许删除的一端
- **队尾**：允许插入的一端

<span style="background-color:#8db3e2">**队列的特性**：先进先出（First In First Out，FIFO）</span>

### 4.2 队列的基本操作

| 操作 | 描述 |
|------|------|
| `InitQueue(&Q)` | 初始化队列 |
| `DestroyQueue(&Q)` | 销毁队列 |
| `EnQueue(&Q, x)` | 入队，元素 $x$ 加入队尾 |
| `DeQueue(&Q, &x)` | 出队，队头元素出队，用 $x$ 返回 |
| `GetHead(Q, &x)` | 读队头元素 |
| `QueueEmpty(Q)` | 判断队列是否为空 |

---

## 5. 顺序队列

### 5.1 顺序队列的定义

```c
#define MaxSize 100
typedef struct {
    ElemType data[MaxSize];
    int front, rear;
} SqQueue;
```

**初始化**：`Q.front = Q.rear = 0`

### 5.2 顺序队列的问题

<span style="background-color:#ccc1d9">**假溢出**</span>：队列未满但无法入队的现象。

**解决方案**：使用<span style="background-color:#ccc1d9">**循环队列**</span>

### 5.3 循环队列

#### 5.3.1 循环队列的定义

```c
typedef struct {
    ElemType data[MaxSize];
    int front, rear;
} SqQueue;
```

#### 5.3.2 循环队列的判空和判满

**方案一**：少用一个元素空间

- 判空：`Q.front == Q.rear`
- 判满：`(Q.rear + 1) % MaxSize == Q.front`

#### 5.3.3 循环队列的入队操作

```c
bool EnQueue(SqQueue &Q, ElemType x) {
    if ((Q.rear + 1) % MaxSize == Q.front) return false;
    Q.data[Q.rear] = x;
    Q.rear = (Q.rear + 1) % MaxSize;
    return true;
}
```

#### 5.3.4 循环队列的出队操作

```c
bool DeQueue(SqQueue &Q, ElemType &x) {
    if (Q.front == Q.rear) return false;
    x = Q.data[Q.front];
    Q.front = (Q.front + 1) % MaxSize;
    return true;
}
```

---

## 6. 链队列

### 6.1 链队列的定义

```c
typedef struct LinkNode {
    ElemType data;
    struct LinkNode *next;
} LinkNode;

typedef struct {
    LinkNode *front, *rear;
} LinkQueue;
```

### 6.2 链队列的入队操作

```c
bool EnQueue(LinkQueue &Q, ElemType x) {
    LinkNode *s = (LinkNode*)malloc(sizeof(LinkNode));
    s->data = x;
    s->next = NULL;
    Q.rear->next = s;
    Q.rear = s;
    return true;
}
```

### 6.3 链队列的出队操作

```c
bool DeQueue(LinkQueue &Q, ElemType &x) {
    if (Q.front == Q.rear) return false;
    LinkNode *p = Q.front->next;
    x = p->data;
    Q.front->next = p->next;
    if (Q.rear == p) Q.rear = Q.front;
    free(p);
    return true;
}
```

---

## 7. 栈和队列的应用

### 7.1 栈的应用

#### 7.1.1 括号匹配

```c
bool bracketCheck(char str[], int length) {
    SqStack S;
    InitStack(S);
    for (int i = 0; i < length; i++) {
        if (str[i] == '(' || str[i] == '[' || str[i] == '{') {
            Push(S, str[i]);
        } else {
            if (StackEmpty(S)) return false;
            char topElem;
            Pop(S, topElem);
            if (str[i] == ')' && topElem != '(') return false;
            if (str[i] == ']' && topElem != '[') return false;
            if (str[i] == '}' && topElem != '{') return false;
        }
    }
    return StackEmpty(S);
}
```

#### 7.1.2 表达式求值

**后缀表达式求值**：

```c
int evalRPN(char **tokens, int tokensSize) {
    int stack[10000], top = -1;
    for (int i = 0; i < tokensSize; i++) {
        if (tokens[i][0] >= '0' && tokens[i][0] <= '9' || 
            (tokens[i][0] == '-' && strlen(tokens[i]) > 1)) {
            stack[++top] = atoi(tokens[i]);
        } else {
            int b = stack[top--];
            int a = stack[top--];
            switch(tokens[i][0]) {
                case '+': stack[++top] = a + b; break;
                case '-': stack[++top] = a - b; break;
                case '*': stack[++top] = a * b; break;
                case '/': stack[++top] = a / b; break;
            }
        }
    }
    return stack[top];
}
```

#### 7.1.3 递归转迭代

利用栈模拟递归调用过程。

### 7.2 队列的应用

#### 7.2.1 层次遍历

二叉树的层次遍历需要使用队列。

#### 7.2.2 任务调度

操作系统中的进程调度、打印队列等。

#### 7.2.3 广度优先搜索

图的广度优先搜索需要使用队列。

---

## 8. 典型例题

### 例题 1：栈的出栈序列判断

**题目**：已知栈的输入序列为 `a,b,c,d,e`，判断下列哪些是合法的出栈序列。

**思路**：模拟栈操作，判断是否能得到目标序列。

**解答**：

```c
bool isValidPopSequence(int push[], int pop[], int n) {
    int stack[100], top = -1;
    int j = 0;
    for (int i = 0; i < n; i++) {
        stack[++top] = push[i];
        while (top >= 0 && stack[top] == pop[j]) {
            top--;
            j++;
        }
    }
    return top == -1;
}
```

**总结**：合法出栈序列的个数为卡特兰数 $\frac{1}{n+1}C_{2n}^n$。

**来源**：408历年真题，考查方式：选择题

---

### 例题 2：用两个栈实现队列

**题目**：用两个栈实现一个队列，支持队列的基本操作（push、pop、peek、empty）。

**思路**：栈1负责入队，栈2负责出队。

**解答**：

```c
typedef struct {
    int stack1[100];
    int stack2[100];
    int top1;
    int top2;
} MyQueue;

void myQueuePush(MyQueue* obj, int x) {
    obj->stack1[++obj->top1] = x;
}

int myQueuePop(MyQueue* obj) {
    if (obj->top2 == -1) {
        while (obj->top1 != -1) {
            obj->stack2[++obj->top2] = obj->stack1[obj->top1--];
        }
    }
    return obj->stack2[obj->top2--];
}
```

**总结**：入队 $O(1)$，出队均摊 $O(1)$。

**来源**：408历年真题，考查方式：算法设计

---

### 例题 3：滑动窗口最大值

**题目**：给定一个数组和滑动窗口的大小，找出所有滑动窗口里的最大值。

**思路**：使用单调队列维护窗口内的最大值。

**解答**：

```c
int* maxSlidingWindow(int* nums, int numsSize, int k, int* returnSize) {
    int *res = (int*)malloc((numsSize - k + 1) * sizeof(int));
    int *q = (int*)malloc(numsSize * sizeof(int));
    int front = 0, rear = 0, idx = 0;
    for (int i = 0; i < numsSize; i++) {
        while (front < rear && nums[i] >= nums[q[rear-1]]) rear--;
        q[rear++] = i;
        while (q[front] <= i - k) front++;
        if (i >= k - 1) res[idx++] = nums[q[front]];
    }
    *returnSize = idx;
    return res;
}
```

**总结**：单调队列是解决滑动窗口问题的常用技巧。

**来源**：408历年真题，考查方式：算法设计

---

> **注**：本 Lecture 内容涵盖栈和队列的基本概念、顺序存储、链式存储、应用场景等知识点。建议结合王道《数据结构》和408历年真题进行练习巩固。