---
title: "Lecture 03 - 树与二叉树"
date: "2026-06-17"
category: "数据结构"
  - 王道《数据结构》
  - 408历年真题
  - 《数据结构》严蔚敏
difficulty: 基础
---

## 1. 树的基本概念

### 1.1 树的定义

<span style="background-color:#ccc1d9">**树**</span>是 $n(n \geq 0)$ 个结点的有限集合。当 $n = 0$ 时，称为空树；当 $n > 0$ 时，有且仅有一个根结点，其余结点分为 $m(m \geq 0)$ 个互不相交的子树。

### 1.2 树的基本术语

| 术语 | 定义 |
|------|------|
| **结点的度** | 结点拥有的子树数目 |
| **树的度** | 树中所有结点的最大度数 |
| **叶子结点** | 度为0的结点 |
| **分支结点** | 度不为0的结点 |
| **孩子/双亲** | 子树的根称为孩子，该结点称为双亲 |
| **兄弟** | 同一个双亲的孩子之间互称兄弟 |
| **祖先/子孙** | 从根到该结点所经分支上的所有结点为祖先；该结点所有子树上的结点为子孙 |
| **层次** | 根为第1层，其孩子为第2层，以此类推 |
| **树的高度** | 树中结点的最大层次 |
| **森林** | $m(m \geq 0)$ 棵互不相交的树的集合 |

### 1.3 树的性质

<span style="background-color:#8db3e2">**性质1**：树的结点数 = 总度数 + 1</span>

<span style="background-color:#8db3e2">**性质2**：度为 $m$ 的树中第 $i$ 层最多有 $m^{i-1}$ 个结点</span>

<span style="background-color:#8db3e2">**性质3**：高度为 $h$ 的 $m$ 叉树最多有 $\frac{m^h - 1}{m - 1}$ 个结点</span>

---

## 2. 二叉树的定义

### 2.1 二叉树的定义

<span style="background-color:#ccc1d9">**二叉树**</span>是 $n(n \geq 0)$ 个结点的有限集合：
- 或者为空二叉树（$n = 0$）
- 或者由一个根结点和两个互不相交的左子树、右子树组成

**特点**：
- 每个结点至多只有两棵子树
- 左右子树不能颠倒（二叉树是有序树）

### 2.2 几种特殊的二叉树

#### 2.2.1 满二叉树

<span style="background-color:#ccc1d9">**满二叉树**</span>：高度为 $h$，且含有 $2^h - 1$ 个结点的二叉树。

**特点**：
- 只有最后一层有叶子结点
- 不存在度为1的结点

#### 2.2.2 完全二叉树

<span style="background-color:#ccc1d9">**完全二叉树**</span>：当且仅当其每个结点都与高度为 $h$ 的满二叉树中编号为1～$n$ 的结点一一对应。

**特点**：
- 只有最后两层可能有叶子结点
- 最多只有一个度为1的结点
- 若某结点只有一个孩子，则一定是左孩子

#### 2.2.3 二叉排序树

<span style="background-color:#ccc1d9">**二叉排序树**</span>：左子树所有结点关键字 < 根结点关键字 < 右子树所有结点关键字。

#### 2.2.4 平衡二叉树

<span style="background-color:#ccc1d9">**平衡二叉树**</span>：任一结点的左右子树深度差不超过1。

### 2.3 二叉树的性质

<span style="background-color:#8db3e2">**性质1**：非空二叉树的叶子结点数 = 度为2的结点数 + 1，即 $n_0 = n_2 + 1$</span>

<span style="background-color:#8db3e2">**性质2**：二叉树的第 $i$ 层最多有 $2^{i-1}$ 个结点</span>

<span style="background-color:#8db3e2">**性质3**：高度为 $h$ 的二叉树最多有 $2^h - 1$ 个结点</span>

<span style="background-color:#8db3e2">**性质4**：对完全二叉树中编号为 $i$ 的结点：
- 若 $i = 1$，则为根结点；否则，双亲为 $\lfloor i/2 \rfloor$
- 若 $2i \leq n$，则左孩子为 $2i$；否则无左孩子
- 若 $2i+1 \leq n$，则右孩子为 $2i+1$；否则无右孩子</span>

---

## 3. 二叉树的存储结构

### 3.1 顺序存储结构

```c
#define MaxSize 100
typedef struct {
    ElemType data[MaxSize];
    int n;
} SqBiTree;
```

**适用场景**：完全二叉树

### 3.2 链式存储结构

```c
typedef struct BiTNode {
    ElemType data;
    struct BiTNode *lchild, *rchild;
} BiTNode, *BiTree;
```

---

## 4. 二叉树的遍历

### 4.1 先序遍历（NLR）

**顺序**：根 → 左 → 右

```c
void PreOrder(BiTree T) {
    if (T != NULL) {
        visit(T);
        PreOrder(T->lchild);
        PreOrder(T->rchild);
    }
}
```

### 4.2 中序遍历（LNR）

**顺序**：左 → 根 → 右

```c
void InOrder(BiTree T) {
    if (T != NULL) {
        InOrder(T->lchild);
        visit(T);
        InOrder(T->rchild);
    }
}
```

### 4.3 后序遍历（LRN）

**顺序**：左 → 右 → 根

```c
void PostOrder(BiTree T) {
    if (T != NULL) {
        PostOrder(T->lchild);
        PostOrder(T->rchild);
        visit(T);
    }
}
```

### 4.4 层序遍历

**顺序**：从上到下，从左到右

```c
void LevelOrder(BiTree T) {
    LinkQueue Q;
    InitQueue(Q);
    if (T != NULL) EnQueue(Q, T);
    while (!QueueEmpty(Q)) {
        DeQueue(Q, T);
        visit(T);
        if (T->lchild != NULL) EnQueue(Q, T->lchild);
        if (T->rchild != NULL) EnQueue(Q, T->rchild);
    }
}
```

### 4.5 由遍历序列构造二叉树

<span style="background-color:#8db3e2">**定理**：由先序序列和中序序列，或由后序序列和中序序列，可以唯一确定一棵二叉树。</span>

---

## 5. 二叉树的应用

### 5.1 线索二叉树

#### 5.1.1 线索二叉树的定义

<span style="background-color:#ccc1d9">**线索二叉树**</span>：利用二叉树中的空指针域，存放结点在某种遍历序列中的前驱和后继信息。

```c
typedef struct ThreadNode {
    ElemType data;
    struct ThreadNode *lchild, *rchild;
    int ltag, rtag;
} ThreadNode, *ThreadTree;
```

- `ltag = 0`：`lchild` 指向左孩子；`ltag = 1`：`lchild` 指向前驱
- `rtag = 0`：`rchild` 指向右孩子；`rtag = 1`：`rchild` 指向后继

#### 5.1.2 中序线索化

```c
void InThread(ThreadTree &p, ThreadTree &pre) {
    if (p != NULL) {
        InThread(p->lchild, pre);
        if (p->lchild == NULL) {
            p->lchild = pre;
            p->ltag = 1;
        }
        if (pre != NULL && pre->rchild == NULL) {
            pre->rchild = p;
            pre->rtag = 1;
        }
        pre = p;
        InThread(p->rchild, pre);
    }
}
```

### 5.2 哈夫曼树

#### 5.2.1 哈夫曼树的定义

<span style="background-color:#ccc1d9">**哈夫曼树**</span>：带权路径长度最小的二叉树。

**带权路径长度**：树中所有叶子结点的带权路径长度之和。

#### 5.2.2 哈夫曼树的构造

**步骤**：
1. 将 $n$ 个结点作为 $n$ 棵二叉树的森林
2. 每次选取两棵权值最小的树合并
3. 重复步骤2，直到只剩一棵树

#### 5.2.3 哈夫曼编码

**前缀编码**：任一编码都不是其他编码的前缀。

**哈夫曼编码**：利用哈夫曼树构造的前缀编码，可使电文总长度最短。

---

## 6. 树和森林

### 6.1 树的存储结构

#### 6.1.1 双亲表示法

```c
#define MaxSize 100
typedef struct {
    ElemType data;
    int parent;
} PTNode;
typedef struct {
    PTNode nodes[MaxSize];
    int n;
} PTree;
```

#### 6.1.2 孩子表示法

```c
typedef struct CTNode {
    int child;
    struct CTNode *next;
} *ChildPtr;
typedef struct {
    ElemType data;
    ChildPtr firstchild;
} CTBox;
typedef struct {
    CTBox nodes[MaxSize];
    int n, r;
} CTree;
```

#### 6.1.3 孩子兄弟表示法

```c
typedef struct CSNode {
    ElemType data;
    struct CSNode *firstchild, *nextsibling;
} CSNode, *CSTree;
```

### 6.2 树、森林与二叉树的转换

#### 6.2.1 树转二叉树

**规则**：
- 每个结点的左孩子是其第一个孩子
- 每个结点的右孩子是其下一个兄弟

#### 6.2.2 森林转二叉树

**规则**：
- 将森林中每棵树转为二叉树
- 第一棵树不动，后续树依次作为前一棵树的右孩子

#### 6.2.3 二叉树转树/森林

**规则**：
- 若结点 $x$ 是双亲 $y$ 的左孩子，则 $x$ 的右孩子、右孩子的右孩子...都是 $y$ 的孩子

---

## 7. 典型例题

### 例题 1：由先序和中序序列构造二叉树

**题目**：已知先序序列为 `ABDECF`，中序序列为 `DBEAFC`，构造二叉树。

**思路**：先序序列的第一个元素是根，在中序序列中找到根，左边是左子树，右边是右子树。

**解答**：

```c
BiTree BuildTree(char pre[], char in[], int preL, int preR, int inL, int inR) {
    if (preL > preR) return NULL;
    BiTree T = (BiTree)malloc(sizeof(BiTNode));
    T->data = pre[preL];
    int k;
    for (k = inL; k <= inR; k++) {
        if (in[k] == pre[preL]) break;
    }
    int numLeft = k - inL;
    T->lchild = BuildTree(pre, in, preL+1, preL+numLeft, inL, k-1);
    T->rchild = BuildTree(pre, in, preL+numLeft+1, preR, k+1, inR);
    return T;
}
```

**总结**：递归分治是解决此类问题的关键。

**来源**：408历年真题，考查方式：综合题

---

### 例题 2：求二叉树的深度

**题目**：求二叉树的深度。

**思路**：树的深度 = max(左子树深度, 右子树深度) + 1

**解答**：

```c
int TreeDepth(BiTree T) {
    if (T == NULL) return 0;
    int l = TreeDepth(T->lchild);
    int r = TreeDepth(T->rchild);
    return l > r ? l + 1 : r + 1;
}
```

**总结**：后序遍历的典型应用。

**来源**：408历年真题，考查方式：算法设计

---

### 例题 3：哈夫曼编码

**题目**：给定字符频率 `{a:5, b:25, c:3, d:6, e:10, f:11, g:36, h:4}`，构造哈夫曼树并求编码。

**思路**：按权值从小到大合并。

**解答**：

```
哈夫曼树结构（左0右1）：
        100
      /    \
     36(g)  64
           /  \
          25(b) 39
               /  \
              19   20
             / \  / \
            9   10(e) 11(f)
           / \
          4(h) 5(a)
               / \
              3(c) 6(d)

编码：
a: 11100  b: 10  c: 111010  d: 111011  
e: 1100   f: 1101  g: 0  h: 1111
```

**总结**：哈夫曼树中权值越大的结点离根越近。

**来源**：408历年真题，考查方式：综合题

---

> **注**：本 Lecture 内容涵盖树的基本概念、二叉树的定义和性质、二叉树的遍历、线索二叉树、哈夫曼树等知识点。建议结合王道《数据结构》和408历年真题进行练习巩固。