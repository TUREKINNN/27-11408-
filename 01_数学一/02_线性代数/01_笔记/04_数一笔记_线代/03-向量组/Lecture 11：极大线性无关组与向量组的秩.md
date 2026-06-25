---
title: "Lecture 11：极大线性无关组与向量组的秩"
subject: 线性代数
chapter: 03-向量组
difficulty: medium
exam_focus: true
created: 2026-06-16
---

# Lecture 11：极大线性无关组与向量组的秩

## 一、极大线性无关组

### 1.1 定义

> 设向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的一个**部分组** $\boldsymbol{\alpha}_{i_1}, \boldsymbol{\alpha}_{i_2}, \cdots, \boldsymbol{\alpha}_{i_r}$ 满足：
> 1. 该部分组**线性无关**
> 2. 向量组中**任意一个向量**都能由该部分组线性表示
>
> 则称该部分组为原向量组的一个**极大线性无关组**（简称极大无关组）。

> 极大无关组的定义中"极大"的含义是：**再添加任何一个原向量组中的向量，都会变得线性相关**。

### 1.2 极大无关组的性质

1. **不唯一性**：一个向量组的极大无关组一般不唯一
2. **等价性**：不同极大无关组之间互相等价（可以互相线性表示）
3. **个数相同**：不同极大无关组所含向量个数相同
4. **原组线性无关时**：极大无关组就是原向量组本身
5. **含零向量时**：零向量一定不在极大无关组中

> - 若向量组线性无关，则其极大无关组就是它自身
> - 若向量组全为零向量，则没有极大无关组（空集）

### 1.3 求极大无关组的方法

> 1. 将向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 作为**列向量**构成矩阵 $A$
> 2. 对 $A$ 做**初等行变换**化为行阶梯形矩阵 $B$
> 3. $B$ 中**主元所在的列**对应的原向量组中的向量构成一个极大无关组

> 构造矩阵时，必须将向量作为**列**排入矩阵。行变换不改变列向量之间的线性关系。

**步骤详解**：

设 $A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$，行变换得到行阶梯形 $B$：

$$B = \begin{pmatrix} \boxed{*} & * & * & * & * \\ 0 & \boxed{*} & * & * & * \\ 0 & 0 & 0 & \boxed{*} & * \\ 0 & 0 & 0 & 0 & 0 \end{pmatrix}$$

主元在第 1、2、4 列，则 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_4$ 是一个极大无关组。

---

## 二、向量组的秩

### 2.1 定义

> 向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的**极大线性无关组**中所含向量的个数，称为该向量组的**秩**，记为 $r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$。

### 2.2 秩的基本性质

1. $0 \leq r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) \leq \min(s, n)$（$n$ 为向量维数）
2. $r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) = s \iff$ 向量组线性无关
3. $r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) < s \iff$ 向量组线性相关
4. 若向量组 $A$ 能由向量组 $B$ 线性表示，则 $r(A) \leq r(B)$

---

## 三、向量组的秩与矩阵的秩的关系

### 3.1 核心定理

> 设矩阵 $A$ 的行向量组为 $\boldsymbol{\gamma}_1, \boldsymbol{\gamma}_2, \cdots, \boldsymbol{\gamma}_m$，列向量组为 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$，则
> $$\boxed{r(A) = r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n) = r(\boldsymbol{\gamma}_1, \boldsymbol{\gamma}_2, \cdots, \boldsymbol{\gamma}_m)}$$
> 即**矩阵的秩 = 行向量组的秩 = 列向量组的秩**。

### 3.2 推论

> 1. $r(AB) \leq \min(r(A), r(B))$
> 2. 若 $P$ 可逆，则 $r(PA) = r(A)$；若 $Q$ 可逆，则 $r(AQ) = r(A)$
> 3. 初等变换不改变矩阵的秩

### 3.3 行秩、列秩、秩三者等价

| 概念 | 含义 |
|------|------|
| 行秩 | 行向量组的秩 |
| 列秩 | 列向量组的秩 |
| 秩 | 矩阵的秩（非零子式的最高阶数） |

三者恒等，这是线性代数中一个深刻的结果。

---

## 四、向量组秩的计算方法

### 4.1 方法一：行变换法（最常用）

1. 将向量作为**列向量**排成矩阵
2. 初等行变换化为阶梯形
3. 非零行个数 = 秩

### 4.2 方法二：子式法

1. 找到矩阵中**不为零**的 $r$ 阶子式
2. 验证所有 $r+1$ 阶子式（若存在）都为零
3. 则秩为 $r$

### 4.3 方法三：利用已知结论

- $r(A) = 0 \iff A = O$
- $r(A) = 1 \iff A$ 的所有行（列）成比例
- $n$ 阶方阵 $A$：$r(A) = n \iff |A| \neq 0 \iff A$ 可逆

---

## 五、典型例题

### 例1：求极大无关组

设 $\boldsymbol{\alpha}_1 = (1, 2, 1, 0)^T$，$\boldsymbol{\alpha}_2 = (1, 1, 1, 2)^T$，$\boldsymbol{\alpha}_3 = (3, 4, 3, 4)^T$，$\boldsymbol{\alpha}_4 = (1, 3, 1, -2)^T$。求一个极大无关组和向量组的秩。

**解**：

$$A = \begin{pmatrix} 1 & 1 & 3 & 1 \\ 2 & 1 & 4 & 3 \\ 1 & 1 & 3 & 1 \\ 0 & 2 & 4 & -2 \end{pmatrix}$$

行变换：

$$\xrightarrow{r_2 - 2r_1, r_3 - r_1} \begin{pmatrix} 1 & 1 & 3 & 1 \\ 0 & -1 & -2 & 1 \\ 0 & 0 & 0 & 0 \\ 0 & 2 & 4 & -2 \end{pmatrix}$$

$$\xrightarrow{r_4 + 2r_2} \begin{pmatrix} 1 & 1 & 3 & 1 \\ 0 & -1 & -2 & 1 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

主元在第 1、2 列，故 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 是一个极大无关组，$r = 2$。

**验证**：$\boldsymbol{\alpha}_3 = 2\boldsymbol{\alpha}_1 + \boldsymbol{\alpha}_2$，$\boldsymbol{\alpha}_4 = 2\boldsymbol{\alpha}_1 - \boldsymbol{\alpha}_2$。

### 例2：矩阵秩与向量组秩的关系

设 $A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & -2 \\ 3 & 6 & -3 \end{pmatrix}$，求列向量组的秩和行向量组的秩。

**解**：

$$A \xrightarrow{r_2 - 2r_1, r_3 - 3r_1} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 1$。列向量组的秩 = 行向量组的秩 = 1。

**注意**：$r(A) = 1$ 说明所有列向量成比例，所有行向量也成比例。

### 例3：含参求秩

设 $A = \begin{pmatrix} 1 & 2 & a \\ 2 & 3 & b \\ 1 & 1 & c \end{pmatrix}$，$r(A) = 2$，求 $a, b, c$ 的关系。

**解**：

$$A \xrightarrow{r_2 - 2r_1, r_3 - r_1} \begin{pmatrix} 1 & 2 & a \\ 0 & -1 & b-2a \\ 0 & -1 & c-a \end{pmatrix} \xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 2 & a \\ 0 & -1 & b-2a \\ 0 & 0 & c-a-(b-2a) \end{pmatrix}$$

$$= \begin{pmatrix} 1 & 2 & a \\ 0 & -1 & b-2a \\ 0 & 0 & a-b+c \end{pmatrix}$$

$r(A) = 2$ 要求第三行全零，即 $a - b + c = 0$。

### 例4：利用秩判定线性表示

设 $\boldsymbol{\alpha}_1 = (1, 0, 2, 3)^T$，$\boldsymbol{\alpha}_2 = (1, 1, 3, 5)^T$，$\boldsymbol{\alpha}_3 = (1, -1, a+2, 1)^T$，$\boldsymbol{\alpha}_4 = (1, 2, 4, a+8)^T$，$\boldsymbol{\beta} = (1, 1, b+5, 7)^T$。

(1) $a, b$ 为何值时，$\boldsymbol{\beta}$ 不能由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3, \boldsymbol{\alpha}_4$ 线性表示？
(2) $a, b$ 为何值时，$\boldsymbol{\beta}$ 能由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3, \boldsymbol{\alpha}_4$ 唯一线性表示？

**解**：令 $A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3, \boldsymbol{\alpha}_4)$，考察 $r(A)$ 与 $r(A|\boldsymbol{\beta})$。

$$\bar{A} = \begin{pmatrix} 1 & 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & 2 & 1 \\ 2 & 3 & a+2 & 4 & b+5 \\ 3 & 5 & 1 & a+8 & 7 \end{pmatrix}$$

$$\xrightarrow{r_3 - 2r_1, r_4 - 3r_1} \begin{pmatrix} 1 & 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & 2 & 1 \\ 0 & 1 & a & 2 & b+3 \\ 0 & 2 & -2 & a+5 & 4 \end{pmatrix}$$

$$\xrightarrow{r_3 - r_2, r_4 - 2r_2} \begin{pmatrix} 1 & 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & 2 & 1 \\ 0 & 0 & a+1 & 0 & b+2 \\ 0 & 0 & 0 & a+1 & 2 \end{pmatrix}$$

**(1)** $\boldsymbol{\beta}$ 不能线性表示 $\iff r(A) \neq r(A|\boldsymbol{\beta})$。

当 $a = -1, b \neq 0$ 时：$r(A) = 2$，$r(A|\boldsymbol{\beta}) = 3$，不能表示。

**(2)** 唯一表示 $\iff r(A) = r(A|\boldsymbol{\beta}) = 4$。

当 $a \neq -1$ 时，$r(A) = 4 = r(A|\boldsymbol{\beta})$，唯一表示。

---

## 六、易错点总结

> 求极大无关组时，**必须**将向量作为**列**排入矩阵，然后做**行变换**。
> 若作为行排入，行变换会改变行向量之间的线性关系！

> 同一个向量组可能有多个不同的极大无关组，但它们含有的向量个数相同。

> - $r(A+B) \leq r(A) + r(B)$
> - $r(AB) \leq \min(r(A), r(B))$
> - $r(A) + r(B) - n \leq r(AB)$（$A$ 为 $m \times n$，$B$ 为 $n \times p$）

> 求出极大无关组后，还需要将不属于极大无关组的向量用极大无关组**线性表示**。
> 表示系数来自行最简形矩阵中对应列的系数。

---

## 七、知识框架

```
极大无关组与秩
├── 极大无关组
│   ├── 定义：部分组无关 + 任意向量可被表示
│   ├── 不唯一，但含向量个数唯一
│   └── 求法：行变换 → 主元列
├── 向量组的秩
│   ├── 极大无关组的向量个数
│   └── 0 ≤ r ≤ min(s, n)
└── 矩阵的秩 = 行秩 = 列秩
    └── 行变换法 / 子式法
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 10：向量与向量组的线性相关性]] — 线性相关
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 12：等价向量组]] — 等价
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 9：矩阵的秩]] — 矩阵的秩
