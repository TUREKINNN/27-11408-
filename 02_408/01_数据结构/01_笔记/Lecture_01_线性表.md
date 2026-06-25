---
title: "Lecture 01 - 线性表"
date: "2026-06-17"
category: "数据结构"
  - 王道《数据结构》
  - 408历年真题
  - 《数据结构》严蔚敏
difficulty: 基础
---

## 1. 线性表的定义

### 1.1 线性表的基本概念

<span style="background-color:#ccc1d9">**线性表**</span>是具有相同数据类型的 $n(n \geq 0)$ 个数据元素的有限序列，其中 $n$ 为表长，当 $n = 0$ 时线性表是空表。若用 $L$ 命名线性表，则其一般表示为：

$$
L = (a_1, a_2, \dots, a_i, a_{i+1}, \dots, a_n)
$$

- $a_i$ 是第 $i$ 个元素，$i$ 称为位序
- 第一个元素 $a_1$ 是表头，最后一个元素 $a_n$ 是表尾
- 相邻元素之间存在**线性关系**

### 1.2 线性表的基本操作

| 操作 | 描述 |
|------|------|
| `InitList(&L)` | 初始化表，构造空线性表 |
| `DestroyList(&L)` | 销毁线性表，释放内存 |
| `ListInsert(&L, i, e)` | 在第 $i$ 个位置插入元素 $e$ |
| `ListDelete(&L, i, &e)` | 删除第 $i$ 个元素，用 $e$ 返回 |
| `LocateElem(L, e)` | 按值查找，返回元素位序 |
| `GetElem(L, i, &e)` | 按位查找，返回第 $i$ 个元素 |
| `Length(L)` | 返回表长 |
| `PrintList(L)` | 输出所有元素 |
| `Empty(L)` | 判断是否为空表 |

---

## 2. 顺序表

### 2.1 顺序表的定义

<span style="background-color:#ccc1d9">**顺序表**</span>是用一组地址连续的存储单元依次存储线性表的数据元素。

```c
#define MaxSize 100
typedef struct {
    ElemType data[MaxSize];
    int length;
} SqList;
```

### 2.2 顺序表的基本操作

#### 2.2.1 插入操作

```c
bool ListInsert(SqList &L, int i, ElemType e) {
    if (i < 1 || i > L.length + 1) return false;
    if (L.length >= MaxSize) return false;
    for (int j = L.length; j >= i; j--) {
        L.data[j] = L.data[j - 1];
    }
    L.data[i - 1] = e;
    L.length++;
    return true;
}
```

**时间复杂度**：最好 $O(1)$（表头），最坏 $O(n)$（表尾），平均 $O(n)$

#### 2.2.2 删除操作

```c
bool ListDelete(SqList &L, int i, ElemType &e) {
    if (i < 1 || i > L.length) return false;
    e = L.data[i - 1];
    for (int j = i; j < L.length; j++) {
        L.data[j - 1] = L.data[j];
    }
    L.length--;
    return true;
}
```

**时间复杂度**：最好 $O(1)$，最坏 $O(n)$，平均 $O(n)$

#### 2.2.3 查找操作

```c
int LocateElem(SqList L, ElemType e) {
    for (int i = 0; i < L.length; i++) {
        if (L.data[i] == e) return i + 1;
    }
    return 0;
}
```

**时间复杂度**：$O(n)$

---

## 3. 单链表

### 3.1 单链表的定义

<span style="background-color:#ccc1d9">**单链表**</span>是通过指针将若干个结点连接成一个链表。

```c
typedef struct LNode {
    ElemType data;
    struct LNode *next;
} LNode, *LinkList;
```

### 3.2 单链表的基本操作

#### 3.2.1 头插法建立单链表

```c
LinkList List_HeadInsert(LinkList &L) {
    LNode *s; int x;
    L = (LinkList)malloc(sizeof(LNode));
    L->next = NULL;
    scanf("%d", &x);
    while (x != 9999) {
        s = (LNode*)malloc(sizeof(LNode));
        s->data = x;
        s->next = L->next;
        L->next = s;
        scanf("%d", &x);
    }
    return L;
}
```

#### 3.2.2 尾插法建立单链表

```c
LinkList List_TailInsert(LinkList &L) {
    int x;
    L = (LinkList)malloc(sizeof(LNode));
    LNode *s, *r = L;
    scanf("%d", &x);
    while (x != 9999) {
        s = (LNode*)malloc(sizeof(LNode));
        s->data = x;
        r->next = s;
        r = s;
        scanf("%d", &x);
    }
    r->next = NULL;
    return L;
}
```

#### 3.2.3 按序号查找结点

```c
LNode* GetElem(LinkList L, int i) {
    if (i == 0) return L;
    if (i < 1) return NULL;
    LNode *p = L->next;
    int j = 1;
    while (p != NULL && j < i) {
        p = p->next;
        j++;
    }
    return p;
}
```

#### 3.2.4 按值查找结点

```c
LNode* LocateElem(LinkList L, ElemType e) {
    LNode *p = L->next;
    while (p != NULL && p->data != e) {
        p = p->next;
    }
    return p;
}
```

---

## 4. 双链表

### 4.1 双链表的定义

<span style="background-color:#ccc1d9">**双链表**</span>每个结点有两个指针域，分别指向前驱和后继。

```c
typedef struct DNode {
    ElemType data;
    struct DNode *prior, *next;
} DNode, *DLinkList;
```

### 4.2 双链表的插入操作

```c
bool DInsertNextDNode(DNode *p, DNode *s) {
    if (p == NULL || s == NULL) return false;
    s->next = p->next;
    if (p->next != NULL) {
        p->next->prior = s;
    }
    s->prior = p;
    p->next = s;
    return true;
}
```

### 4.3 双链表的删除操作

```c
bool DeleteNextDNode(DNode *p) {
    if (p == NULL || p->next == NULL) return false;
    DNode *q = p->next;
    p->next = q->next;
    if (q->next != NULL) {
        q->next->prior = p;
    }
    free(q);
    return true;
}
```

---

## 5. 循环链表

### 5.1 循环单链表

<span style="background-color:#ccc1d9">**循环单链表**</span>的尾结点指针指向头结点。

### 5.2 循环双链表

<span style="background-color:#ccc1d9">**循环双链表**</span>的头结点的 prior 指向尾结点，尾结点的 next 指向头结点。

---

## 6. 顺序表和链表的比较

| 比较维度 | 顺序表 | 链表 |
|----------|--------|------|
| **存储方式** | 连续存储 | 离散存储 |
| **存取方式** | 随机存取 | 顺序存取 |
| **查找速度** | $O(1)$（按位） | $O(n)$ |
| **插入/删除** | $O(n)$ | $O(1)$（已知位置） |
| **空间利用率** | 低（有空闲单元） | 高（按需分配） |
| **适用场景** | 查找频繁，元素稳定 | 频繁插入/删除 |

---

## 7. 典型例题

### 例题 1：合并两个有序顺序表

**题目**：将两个有序顺序表 $A$ 和 $B$ 合并为一个新的有序顺序表 $C$。

**思路**：设置两个指针分别指向 $A$ 和 $B$ 的当前元素，比较后将较小的元素放入 $C$。

**解答**：

```c
void MergeList(SqList A, SqList B, SqList &C) {
    int i = 0, j = 0, k = 0;
    while (i < A.length && j < B.length) {
        if (A.data[i] <= B.data[j]) {
            C.data[k++] = A.data[i++];
        } else {
            C.data[k++] = B.data[j++];
        }
    }
    while (i < A.length) C.data[k++] = A.data[i++];
    while (j < B.length) C.data[k++] = B.data[j++];
    C.length = k;
}
```

**总结**：时间复杂度 $O(m+n)$，空间复杂度 $O(m+n)$。双指针法是合并有序序列的常用技巧。

**来源**：408历年真题，考查方式：算法设计

---

### 例题 2：删除链表中重复的结点

**题目**：在一个有序单链表中，删除所有重复的元素，使得每个元素只出现一次。

**思路**：遍历链表，若当前结点与下一个结点值相同，则删除下一个结点。

**解答**：

```c
void DeleteDuplicates(LinkList &L) {
    if (L == NULL || L->next == NULL) return;
    LNode *p = L->next;
    while (p->next != NULL) {
        if (p->data == p->next->data) {
            LNode *q = p->next;
            p->next = q->next;
            free(q);
        } else {
            p = p->next;
        }
    }
}
```

**总结**：关键在于判断相邻结点是否相等，注意边界条件。

**来源**：408历年真题，考查方式：算法设计

---

### 例题 3：求两个链表的交点

**题目**：给定两个单链表，找出它们的第一个公共结点。

**思路**：分别计算两个链表的长度，让较长的链表先走差值步，然后同时遍历。

**解答**：

```c
LNode* FindFirstCommonNode(LinkList L1, LinkList L2) {
    int len1 = 0, len2 = 0;
    LNode *p1 = L1->next, *p2 = L2->next;
    while (p1 != NULL) { len1++; p1 = p1->next; }
    while (p2 != NULL) { len2++; p2 = p2->next; }
    p1 = L1->next; p2 = L2->next;
    if (len1 > len2) {
        for (int i = 0; i < len1 - len2; i++) p1 = p1->next;
    } else {
        for (int i = 0; i < len2 - len1; i++) p2 = p2->next;
    }
    while (p1 != NULL && p2 != NULL && p1 != p2) {
        p1 = p1->next;
        p2 = p2->next;
    }
    return p1;
}
```

**总结**：利用长度差消除不平衡，时间复杂度 $O(m+n)$。

**来源**：408历年真题，考查方式：算法设计

---

> **注**：本 Lecture 内容涵盖线性表的基本概念、顺序表、单链表、双链表、循环链表等知识点。建议结合王道《数据结构》和408历年真题进行练习巩固。