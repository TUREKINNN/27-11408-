---
title: "Lecture 12：等价向量组"
subject: 线性代数
chapter: 03-向量组
difficulty: medium
exam_focus: true
created: 2026-06-16
---

# Lecture 12：等价向量组

## 一、等价向量组的定义

### 1.1 定义

> 设有两个向量组：
> - $(\text{I})$：$\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$
> - $(\text{II})$：$\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_t$
>
> 若向量组 $(\text{I})$ 中的每一个向量都能由向量组 $(\text{II})$ 线性表示，
> **且**向量组 $(\text{II})$ 中的每一个向量都能由向量组 $(\text{I})$ 线性表示，
> 则称向量组 $(\text{I})$ 与向量组 $(\text{II})$ **等价**，记为 $(\text{I}) \cong (\text{II})$。

> 等价必须是**互相**线性表示，即**双向**。单向的线性表示不构成等价关系。

### 1.2 等价关系的性质

等价向量组满足以下三条性质：

1. **反身性**（自反性）：任何向量组与自身等价，$(\text{I}) \cong (\text{I})$
2. **对称性**：若 $(\text{I}) \cong (\text{II})$，则 $(\text{II}) \cong (\text{I})$
3. **传递性**：若 $(\text{I}) \cong (\text{II})$，$(\text{II}) \cong (\text{III})$，则 $(\text{I}) \cong (\text{III})$

---

## 二、等价向量组的判定

### 2.1 判定定理

> 向量组 $(\text{I})$ 与向量组 $(\text{II})$ 等价的**充要条件**是：
>
> 设 $A = (\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_s)$，$B = (\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_t)$
>
> $$(\text{I}) \cong (\text{II}) \iff r(A) = r(B) = r(A, B)$$

**解释**：
- $r(A) = r(A, B)$：向量组 $(\text{II})$ 的每个向量都能由 $(\text{I})$ 线性表示
- $r(B) = r(A, B)$：向量组 $(\text{I})$ 的每个向量都能由 $(\text{II})$ 线性表示
- 两者合在一起就是等价

### 2.2 必要条件（非充分条件）

> 若向量组 $(\text{I})$ 与 $(\text{II})$ 等价，则：
> $$r(\text{I}) = r(\text{II})$$
> 即**等价的向量组秩相等**。

> **秩相等的向量组不一定等价！**
>
> 反例：$(\text{I}): \boldsymbol{\alpha}_1 = (1, 0)^T$；$(\text{II}): \boldsymbol{\beta}_1 = (0, 1)^T$
>
> 两者秩都为 1，但 $\boldsymbol{\alpha}_1$ 不能由 $\boldsymbol{\beta}_1$ 线性表示，所以不等价。
>
> 但如果两个向量组**维数相同、秩相同、且一个能由另一个线性表示**，则等价。

### 2.3 充分条件

> 若向量组 $(\text{I})$ 能由 $(\text{II})$ 线性表示，且 $r(\text{I}) = r(\text{II})$，则 $(\text{I}) \cong (\text{II})$。

**证明思路**：由 $(\text{I})$ 能由 $(\text{II})$ 表示，得 $r(\text{I}) \leq r(\text{II})$。设 $(\text{II})$ 的极大无关组为 $\boldsymbol{\beta}_{j_1}, \cdots, \boldsymbol{\beta}_{j_r}$，这些向量都能由 $(\text{I})$ 的极大无关组线性表示（因为 $r(\text{I}) = r(\text{II})$），从而 $(\text{II})$ 能由 $(\text{I})$ 表示，等价得证。

---

## 三、等价向量组与等价矩阵的区别

>
> | 概念 | 含义 | 条件 |
> |------|------|------|
> | 向量组等价 | 互相线性表示 | $r(A) = r(B) = r(A,B)$ |
> | 矩阵等价 | $B = PAQ$（$P, Q$ 可逆） | $r(A) = r(B)$（同型矩阵） |
>
> 向量组等价的条件更强（多了 $r(A,B)$ 的要求）。
>
> 但注意：**列向量组等价 $\Rightarrow$ 矩阵等价**（因为秩相等且同型）。

---

## 四、极大无关组与等价的关系

> 向量组与其极大无关组**等价**。

**证明**：
- 极大无关组中的每个向量当然能由原向量组线性表示
- 由极大无关组的定义，原向量组的每个向量都能由极大无关组线性表示

因此，同一向量组的**任意两个极大无关组等价**。

---

## 五、重要推论

### 5.1 向量组的等价与秩的传递

> 若 $(\text{I}) \cong (\text{II})$，则 $r(\text{I}) = r(\text{II})$。

> 若 $(\text{I})$ 能由 $(\text{II})$ 线性表示，则 $r(\text{I}) \leq r(\text{II})$。

### 5.2 向量组等价与齐次方程组

向量组 $(\text{I}): \boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_s$ 与 $(\text{II}): \boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_t$ 等价

$\iff$ 向量方程 $x_1\boldsymbol{\alpha}_1 + \cdots + x_s\boldsymbol{\alpha}_s = \boldsymbol{\beta}_j$（$j = 1, 2, \cdots, t$）和 $y_1\boldsymbol{\beta}_1 + \cdots + y_t\boldsymbol{\beta}_t = \boldsymbol{\alpha}_i$（$i = 1, 2, \cdots, s$）**都有解**。

---

## 六、典型例题

### 例1：判断向量组等价

设 $(\text{I}): \boldsymbol{\alpha}_1 = (1, 0, 2)^T, \boldsymbol{\alpha}_2 = (1, 1, 3)^T$

$(\text{II}): \boldsymbol{\beta}_1 = (1, 1, 3)^T, \boldsymbol{\beta}_2 = (2, 1, 5)^T, \boldsymbol{\beta}_3 = (0, 1, 1)^T$

判断 $(\text{I})$ 与 $(\text{II})$ 是否等价。

**解**：

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \\ 2 & 3 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 2 & 0 \\ 1 & 1 & 1 \\ 3 & 5 & 1 \end{pmatrix}$$

$(A, B) = \begin{pmatrix} 1 & 1 & 1 & 2 & 0 \\ 0 & 1 & 1 & 1 & 1 \\ 2 & 3 & 3 & 5 & 1 \end{pmatrix}$

行变换：$r_3 - 2r_1$:

$$\begin{pmatrix} 1 & 1 & 1 & 2 & 0 \\ 0 & 1 & 1 & 1 & 1 \\ 0 & 1 & 1 & 1 & 1 \end{pmatrix} \xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 1 & 1 & 2 & 0 \\ 0 & 1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 2$，$r(B) = 2$（$B$ 也化简后秩为 2），$r(A, B) = 2$。

$$r(A) = r(B) = r(A, B) = 2$$

所以 $(\text{I})$ 与 $(\text{II})$ **等价**。

**验证**：$\boldsymbol{\beta}_1 = \boldsymbol{\alpha}_2$，$\boldsymbol{\beta}_2 = \boldsymbol{\alpha}_1 + \boldsymbol{\alpha}_2$，$\boldsymbol{\beta}_3 = \boldsymbol{\alpha}_2 - \boldsymbol{\alpha}_1$。

### 例2：秩相等但不等价

设 $(\text{I}): \boldsymbol{\alpha}_1 = (1, 0)^T$

$(\text{II}): \boldsymbol{\beta}_1 = (0, 1)^T$

$r(\text{I}) = r(\text{II}) = 1$，但 $\boldsymbol{\alpha}_1 = (1, 0)^T$ 不能由 $\boldsymbol{\beta}_1 = (0, 1)^T$ 线性表示（不存在 $k$ 使 $(1, 0)^T = k(0, 1)^T$）。

故 $(\text{I})$ 与 $(\text{II})$ **不等价**。


### 例3：利用等价求参数

设 $(\text{I}): \boldsymbol{\alpha}_1 = (1, 2, 3)^T, \boldsymbol{\alpha}_2 = (1, 0, 1)^T$

$(\text{II}): \boldsymbol{\beta}_1 = (1, a, 2)^T, \boldsymbol{\beta}_2 = (0, 1, b)^T$

若 $(\text{I}) \cong (\text{II})$，求 $a, b$。

**解**：等价 $\Rightarrow$ $r(\text{I}) = r(\text{II}) = 2$（因为 $(\text{I})$ 中 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 不成比例，秩为 2）。

$(\text{II})$ 秩为 2 要求 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2$ 不成比例，即 $a \neq \frac{1}{0}$（自动满足）且不成比例。

还需 $r(A, B) = 2$，即 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 能由 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2$ 表示：

$$\boldsymbol{\alpha}_2 = k_1\boldsymbol{\beta}_1 + k_2\boldsymbol{\beta}_2 \Rightarrow (1, 0, 1)^T = k_1(1, a, 2)^T + k_2(0, 1, b)^T$$

$k_1 = 1$，$a + k_2 = 0 \Rightarrow k_2 = -a$，$2 - ab = 1 \Rightarrow ab = 1$。

所以 $a$ 和 $b$ 需满足 $ab = 1$。

---

## 七、易错点总结

> 向量组等价要求**互相**线性表示，不能只验证一个方向。

> 秩相等是等价的**必要条件**，不是**充分条件**。
> 还需要至少一个方向的线性表示成立。

> 等价的向量组不一定含相同个数的向量！
> 例如 $(\text{I}): \boldsymbol{\alpha}_1$ 与 $(\text{II}): \boldsymbol{\beta}_1, \boldsymbol{\beta}_2$（其中 $\boldsymbol{\beta}_1 = \boldsymbol{\alpha}_1, \boldsymbol{\beta}_2 = 2\boldsymbol{\alpha}_1$）

> 两者定义不同，不要混淆。矩阵等价只要求秩相等（同型），向量组等价还需 $r(A,B)$ 条件。

---

## 八、知识框架

```
等价向量组
├── 定义：互相线性表示
├── 判定：r(A) = r(B) = r(A,B)
├── 性质
│   ├── 反身性、对称性、传递性
│   └── 等价 → 秩相等（反之不成立）
├── 极大无关组与原组等价
└── 区别：向量组等价 ≠ 矩阵等价
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 10：向量与向量组的线性相关性]] — 线性相关
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 11：极大线性无关组与向量组的秩]] — 无关组
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 8：等价矩阵]] — 等价矩阵
