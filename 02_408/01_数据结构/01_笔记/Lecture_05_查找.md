---
title: "Lecture 05 - 查找"
date: "2026-06-17"
category: "数据结构"
  - 王道《数据结构》
  - 408历年真题
  - 《数据结构》严蔚敏
difficulty: 基础
---

## 1. 查找的基本概念

### 1.1 查找的定义

<span style="background-color:#ccc1d9">**查找**</span>：在数据集合中寻找满足特定条件的数据元素的过程。

### 1.2 基本术语

| 术语 | 定义 |
|------|------|
| **关键字** | 数据元素中用于标识元素的数据项 |
| **主关键字** | 唯一标识元素的关键字 |
| **次关键字** | 不唯一标识元素的关键字 |
| **平均查找长度（ASL）** | 查找过程中关键字比较次数的平均值 |

$$
ASL = \sum_{i=1}^{n} P_i \cdot C_i
$$

其中 $P_i$ 是查找第 $i$ 个元素的概率，$C_i$ 是查找第 $i$ 个元素所需的比较次数。

---

## 2. 顺序查找

### 2.1 顺序查找的定义

<span style="background-color:#ccc1d9">**顺序查找**</span>：从表的一端开始，逐个比较关键字，直到找到目标或遍历完整个表。

### 2.2 顺序查找的实现

```c
int SeqSearch(int arr[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == key) return i;
    }
    return -1;
}
```

### 2.3 性能分析

**平均查找长度**：

$$
ASL_{成功} = \frac{1}{n} \sum_{i=1}^{n} i = \frac{n+1}{2}
$$

$$
ASL_{失败} = n + 1
$$

**时间复杂度**：$O(n)$

---

## 3. 二分查找

### 3.1 二分查找的定义

<span style="background-color:#ccc1d9">**二分查找**</span>：在有序表中，每次将查找范围缩小一半，直到找到目标或范围为空。

### 3.2 二分查找的实现

```c
int BinarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == key) return mid;
        else if (arr[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

### 3.3 性能分析

**平均查找长度**：

$$
ASL_{成功} = \frac{1}{n} \sum_{i=1}^{h} i \cdot 2^{i-1} \approx \log_2(n+1) - 1
$$

**时间复杂度**：$O(\log n)$

**适用条件**：有序的顺序表

---

## 4. 分块查找

### 4.1 分块查找的定义

<span style="background-color:#ccc1d9">**分块查找**</span>：将表分成若干块，块内无序，块间有序。先确定目标所在块，再在块内顺序查找。

### 4.2 性能分析

**平均查找长度**：

$$
ASL = L_b + L_w
$$

其中 $L_b$ 是块间查找的平均长度，$L_w$ 是块内查找的平均长度。

**时间复杂度**：$O(\sqrt{n})$

---

## 5. 二叉搜索树

### 5.1 二叉搜索树的定义

<span style="background-color:#ccc1d9">**二叉搜索树**</span>：左子树所有结点关键字 < 根结点关键字 < 右子树所有结点关键字。

### 5.2 二叉搜索树的基本操作

#### 5.2.1 查找操作

```c
BSTNode* BSTSearch(BiTree T, int key) {
    while (T != NULL && T->data != key) {
        if (key < T->data) T = T->lchild;
        else T = T->rchild;
    }
    return T;
}
```

#### 5.2.2 插入操作

```c
bool BSTInsert(BiTree &T, int key) {
    if (T == NULL) {
        T = (BiTree)malloc(sizeof(BSTNode));
        T->data = key;
        T->lchild = T->rchild = NULL;
        return true;
    }
    if (key == T->data) return false;
    else if (key < T->data) return BSTInsert(T->lchild, key);
    else return BSTInsert(T->rchild, key);
}
```

### 5.3 性能分析

**平均查找长度**：
- 最好情况（平衡）：$O(\log n)$
- 最坏情况（退化）：$O(n)$

---

## 6. 平衡二叉树

### 6.1 平衡二叉树的定义

<span style="background-color:#ccc1d9">**平衡二叉树**</span>：任一结点的左右子树高度差（平衡因子）的绝对值不超过1。

**平衡因子**：$BF(T) = h_L - h_R$

### 6.2 平衡二叉树的调整

- **LL旋转（右单旋转）**：A的左孩子B的左子树上插入导致失衡
- **RR旋转（左单旋转）**：A的右孩子B的右子树上插入导致失衡
- **LR旋转**：A的左孩子B的右子树上插入导致失衡
- **RL旋转**：A的右孩子B的左子树上插入导致失衡

### 6.3 性能分析

**时间复杂度**：$O(\log n)$

---

## 7. B树和B+树

### 7.1 B树的定义

<span style="background-color:#ccc1d9">**B树**</span>：一棵 $m$ 阶B树是一棵平衡的多路搜索树。

**性质**：
1. 每个结点最多有 $m$ 棵子树
2. 根结点最少有1棵子树，其他结点最少有 $\lceil m/2 \rceil$ 棵子树
3. 所有叶子结点在同一层

### 7.2 B+树

<span style="background-color:#ccc1d9">**B+树**</span>：B树的变体，所有数据都存储在叶子结点中，非叶子结点只存储索引。

**优点**：
- 查找效率稳定（所有查找都到叶子结点）
- 范围查询方便

---

## 8. 哈希查找

### 8.1 哈希表的定义

<span style="background-color:#ccc1d9">**哈希表**</span>：通过哈希函数将关键字映射到存储位置。

### 8.2 哈希函数的构造方法

| 方法 | 描述 |
|------|------|
| **直接定址法** | $H(key) = key$ 或 $H(key) = a \cdot key + b$ |
| **除留余数法** | $H(key) = key \% p$，$p$ 为质数 |
| **数字分析法** | 取关键字的某些位数作为哈希地址 |
| **平方取中法** | 取关键字平方的中间几位作为哈希地址 |

### 8.3 处理冲突的方法

- **开放定址法**：线性探测、二次探测
- **拉链法**：将冲突的元素用链表连接

### 8.4 性能分析

**时间复杂度**：$O(1)$（平均）

---

## 9. 典型例题

### 例题 1：二分查找实现

**题目**：在有序数组 `[1, 3, 5, 7, 9, 11, 13, 15]` 中查找元素7。

**解答**：

```c
int BinarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1;
    while (low <= high) {
        int mid = (low + high) / 2;
        if (arr[mid] == key) return mid;
        else if (arr[mid] < key) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

// 查找过程：
// low=0, high=7, mid=3, arr[3]=7 == key, 返回3
```

**总结**：二分查找效率高，但要求数据有序。

**来源**：408历年真题，考查方式：选择题

---

### 例题 2：二叉搜索树的删除

**题目**：删除二叉搜索树中的结点。

**思路**：根据结点的子树情况选择不同策略。

**解答**：

```c
bool BSTDelete(BiTree &T, int key) {
    if (T == NULL) return false;
    if (key < T->data) return BSTDelete(T->lchild, key);
    else if (key > T->data) return BSTDelete(T->rchild, key);
    else {
        if (T->lchild == NULL) {
            BiTree q = T;
            T = T->rchild;
            free(q);
        } else if (T->rchild == NULL) {
            BiTree q = T;
            T = T->lchild;
            free(q);
        } else {
            BiTree q = T->rchild;
            while (q->lchild != NULL) q = q->lchild;
            T->data = q->data;
            return BSTDelete(T->rchild, q->data);
        }
        return true;
    }
}
```

**总结**：删除有两个孩子的结点时，用右子树的最小结点替换。

**来源**：408历年真题，考查方式：算法设计

---

### 例题 3：哈希查找

**题目**：构造哈希表，处理冲突。

**思路**：选择合适的哈希函数和冲突处理方法。

**解答**：

```c
#define TABLE_SIZE 11

int Hash(int key) {
    return key % TABLE_SIZE;
}

void Insert(int table[], int key) {
    int addr = Hash(key);
    while (table[addr] != -1) {
        addr = (addr + 1) % TABLE_SIZE;
    }
    table[addr] = key;
}

// 插入序列：{19, 14, 23, 1, 68, 20, 84, 27, 55, 11, 10, 79}

// 哈希表：
// index: 0  1  2  3  4  5  6  7  8  9  10
// value: 68 19 27 14 20 84 23 55 1  10 79
//        11

// ASL成功 = (1+1+2+1+1+1+2+1+2+1+1+2)/12 = 1.5
```

**总结**：哈希查找效率高，但需要合理设计哈希函数。

**来源**：408历年真题，考查方式：综合题

---

> **注**：本 Lecture 内容涵盖顺序查找、二分查找、分块查找、二叉搜索树、平衡二叉树、B树、B+树、哈希查找等知识点。建议结合王道《数据结构》和408历年真题进行练习巩固。