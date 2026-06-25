---
title: "Lecture 10：向量与向量组的线性相关性"
subject: 线性代数
chapter: 03-向量组
difficulty: medium
exam_focus: true
created: 2026-06-16
---

# Lecture 10：向量与向量组的线性相关性

## 一、基本概念

### 1.1 向量与向量组

**向量**：$n$ 个数 $a_1, a_2, \cdots, a_n$ 组成的有序数组

$$\boldsymbol{\alpha} = \begin{pmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{pmatrix} \quad \text{（列向量）}$$

**向量组**：若干个同维数的列向量（或行向量）所组成的集合

> 列向量 $\boldsymbol{\alpha} = (a_1, a_2, \cdots, a_n)^T$ 与行向量 $\boldsymbol{\alpha}^T = (a_1, a_2, \cdatrix, a_n)$ 在本质上线性代数中通常默认为**列向量**。

---

## 二、线性组合与线性表示

### 2.1 线性组合

> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 是 $s$ 个 $n$ 维向量，$k_1, k_2, \cdots, k_s$ 是 $s$ 个数，则
> $$k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s$$
> 称为向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的一个**线性组合**，$k_1, k_2, \cdots, k_s$ 称为**组合系数**。

### 2.2 线性表示

> 若向量 $\boldsymbol{\beta}$ 能写成向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的线性组合，即存在数 $k_1, k_2, \cdots, k_s$ 使得
> $$\boldsymbol{\beta} = k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s$$
> 则称 $\boldsymbol{\beta}$ 能由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ **线性表示**（或线性表出）。

### 2.3 线性表示的判定

> 向量 $\boldsymbol{\beta}$ 能由向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性表示
> $$\iff \text{方程组 } x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + \cdots + x_s\boldsymbol{\alpha}_s = \boldsymbol{\beta} \text{ 有解}$$
> $$\iff r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) = r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s, \boldsymbol{\beta})$$

**矩阵形式**：设 $A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$，则 $\boldsymbol{\beta}$ 能由 $A$ 的列向量线性表示 $\iff r(A) = r(A|\boldsymbol{\beta})$。

### 2.4 线性表示的重要性质

1. 零向量可以由任意向量组线性表示（取所有系数为0）
2. 任意向量都可以由单位向量组 $\boldsymbol{e}_1, \boldsymbol{e}_2, \cdots, \boldsymbol{e}_n$ 线性表示
3. 向量组中每个向量都可以由该向量组线性表示

---

## 三、线性相关与线性无关

### 3.1 定义

> 对于向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$，若存在**不全为零**的数 $k_1, k_2, \cdots, k_s$，使得
> $$k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s = \boldsymbol{0}$$
> 则称该向量组**线性相关**。

> 若当且仅当 $k_1 = k_2 = \cdots = k_s = 0$ 时，才有
> $$k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s = \boldsymbol{0}$$
> 则称该向量组**线性无关**（线性独立）。

> 线性相关 = 存在非零解；线性无关 = 只有零解。
> "不全为零"意味着**至少有一个** $k_i \neq 0$。

### 3.2 几何意义

- **$\mathbb{R}^2$ 中两个向量**：线性相关 $\iff$ 两向量共线（平行）；线性无关 $\iff$ 不共线
- **$\mathbb{R}^3$ 中两个向量**：线性相关 $\iff$ 共线；线性无关 $\iff$ 不共线
- **$\mathbb{R}^3$ 中三个向量**：线性相关 $\iff$ 三向量共面；线性无关 $\iff$ 不共面

### 3.3 与线性表示的关系

> 向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$（$s \geq 2$）线性相关
> $$\iff \text{其中至少有一个向量可以由其余 } s-1 \text{ 个向量线性表示}$$

---

## 四、线性相关性的判定定理

### 4.1 定理1：齐次方程组判定法

> 向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性相关
> $$\iff \text{齐次方程组 } x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + \cdots + x_s\boldsymbol{\alpha}_s = \boldsymbol{0} \text{ 有非零解}$$
> $$\iff r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) < s$$

线性无关 $\iff$ 齐次方程组只有零解 $\iff r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) = s$

### 4.2 定理2：个数大于维数

> $n$ 维向量组中，若向量个数 $s > n$，则该向量组**一定线性相关**。

**理解**：$s > n$ 时，$r(A) \leq n < s$，所以 $r(A) < s$，线性相关。

### 4.3 定理3：部分与整体

> - 若向量组中**部分向量组**线性相关，则**整个向量组**线性相关。
> - 若整个向量组线性无关，则其**任何部分向量组**也线性无关。

**逆否命题**：整体无关 $\Rightarrow$ 部分无关；部分相关 $\Rightarrow$ 整体相关。

### 4.4 定理4：增加分量

> 若向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性无关，则在每个向量的**相同位置**添加一个分量后得到的新向量组也线性无关。

即：若 $n$ 维向量组线性无关，则将每个向量扩展为 $n+1$ 维后仍线性无关。

**逆否命题**：降维后若线性相关，则原向量组线性相关。

### 4.5 定理5：含零向量

> 向量组中若含有**零向量**，则该向量组**一定线性相关**。
>
> 特别地，**单个零向量**线性相关；**单个非零向量**线性无关。

### 4.6 定理6：两个向量

> 两个向量线性相关 $\iff$ 它们**成比例**（即对应分量之比相等）。

---

## 五、重要推论与技巧

### 5.1 逐个判定法

判定 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的线性相关性：
1. 令 $A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$
2. 对 $A$ 做初等行变换化为阶梯形
3. 若阶梯形矩阵每列都有主元（$r(A) = s$），则线性无关
4. 若某列无主元（$r(A) < s$），则线性相关

### 5.2 常见结论速查

| 条件 | 结论 |
|------|------|
| $s > n$ | 一定线性相关 |
| 含零向量 | 一定线性相关 |
| $s = 1$，$\boldsymbol{\alpha}_1 \neq \boldsymbol{0}$ | 线性无关 |
| $s = 1$，$\boldsymbol{\alpha}_1 = \boldsymbol{0}$ | 线性相关 |
| $s = 2$，成比例 | 线性相关 |
| $s = 2$，不成比例 | 线性无关 |
| 部分相关 | 整体相关 |
| 整体无关 | 部分无关 |

---

## 六、典型例题

### 例1：线性表示判定

设 $\boldsymbol{\alpha}_1 = (1, 2, 3)^T$，$\boldsymbol{\alpha}_2 = (1, 0, 2)^T$，$\boldsymbol{\alpha}_3 = (1, 4, 4)^T$，$\boldsymbol{\beta} = (2, 2, 5)^T$。

问 $\boldsymbol{\beta}$ 能否由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3$ 线性表示？

**解**：

$$A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3 | \boldsymbol{\beta}) = \begin{pmatrix} 1 & 1 & 1 & 2 \\ 2 & 0 & 4 & 2 \\ 3 & 2 & 4 & 5 \end{pmatrix}$$

初等行变换：

$$\xrightarrow{r_2 - 2r_1, r_3 - 3r_1} \begin{pmatrix} 1 & 1 & 1 & 2 \\ 0 & -2 & 2 & -2 \\ 0 & -1 & 1 & -1 \end{pmatrix}$$

$$\xrightarrow{r_3 - \frac{1}{2}r_2} \begin{pmatrix} 1 & 1 & 1 & 2 \\ 0 & -2 & 2 & -2 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = r(A|\boldsymbol{\beta}) = 2 < 3$，方程组有无穷多解，$\boldsymbol{\beta}$ 能由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3$ 线性表示。

令 $x_3 = t$，由 $-2x_2 + 2t = -2$ 得 $x_2 = t + 1$，$x_1 = 2 - (t+1) - t = 1 - 2t$。

$$\boldsymbol{\beta} = (1-2t)\boldsymbol{\alpha}_1 + (1+t)\boldsymbol{\alpha}_2 + t\boldsymbol{\alpha}_3 \quad (t \text{ 为任意常数})$$

### 例2：线性相关性判定

设 $\boldsymbol{\alpha}_1 = (1, 1, 0)^T$，$\boldsymbol{\alpha}_2 = (0, 1, 1)^T$，$\boldsymbol{\alpha}_3 = (1, 0, -1)^T$，讨论线性相关性。

**解**：

$$A = \begin{pmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & -1 \end{pmatrix} \xrightarrow{r_2 - r_1} \begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & -1 \\ 0 & 1 & -1 \end{pmatrix} \xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & -1 \\ 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 2 < 3$（向量个数），所以 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3$ **线性相关**。

**验证**：$\boldsymbol{\alpha}_3 = \boldsymbol{\alpha}_1 - \boldsymbol{\alpha}_2$，即 $\boldsymbol{\alpha}_1 - \boldsymbol{\alpha}_2 - \boldsymbol{\alpha}_3 = \boldsymbol{0}$。

### 例3：含参讨论

设 $\boldsymbol{\alpha}_1 = (1, a, 0)^T$，$\boldsymbol{\alpha}_2 = (0, 1, b)^T$，$\boldsymbol{\alpha}_3 = (c, 0, 1)^T$，讨论 $a, b, c$ 取何值时线性相关。

**解**：三个三维向量线性相关 $\iff |A| = 0$

$$|A| = \begin{vmatrix} 1 & 0 & c \\ a & 1 & 0 \\ 0 & b & 1 \end{vmatrix} = 1 \cdot (1 - 0) - 0 + c \cdot (ab - 0) = 1 + abc$$

令 $1 + abc = 0$，即 $abc = -1$ 时线性相关。

> $n$ 个 $n$ 维向量的线性相关性可以通过**行列式**判定：
> - $|A| \neq 0 \iff$ 线性无关
> - $|A| = 0 \iff$ 线性相关

### 例4：高维向量的线性相关性

设 $\boldsymbol{\alpha}_1 = (1, 2, 3, 4)^T$，$\boldsymbol{\alpha}_2 = (2, 3, 4, 5)^T$，$\boldsymbol{\alpha}_3 = (3, 4, 5, 6)^T$，$\boldsymbol{\alpha}_4 = (4, 5, 6, 7)^T$，判断线性相关性。

**解**：构造矩阵

$$A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 3 & 4 & 5 \\ 3 & 4 & 5 & 6 \\ 4 & 5 & 6 & 7 \end{pmatrix}$$

逐行消元：

$$\xrightarrow{r_2 - 2r_1, r_3 - 3r_1, r_4 - 4r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -2 & -3 \\ 0 & -2 & -4 & -6 \\ 0 & -3 & -6 & -9 \end{pmatrix}$$

$$\xrightarrow{r_3 - 2r_2, r_4 - 3r_2} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -2 & -3 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 2 < 4$，故 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3, \boldsymbol{\alpha}_4$ **线性相关**。

---

## 七、易错点总结

> 线性相关的定义是存在**不全为零**的系数 $k_1, k_2, \cdots, k_s$，不是**全不为零**！
> 例如 $\boldsymbol{\alpha}_1 = \boldsymbol{0}$，取 $k_1 = 1, k_2 = k_3 = \cdots = 0$ 即可。

> 部分向量组线性相关，可能只是其中某些向量能由其他向量线性表示。

> $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 线性相关 $\iff$ $\boldsymbol{\alpha}_1 = k\boldsymbol{\alpha}_2$ 或 $\boldsymbol{\alpha}_2 = k\boldsymbol{\alpha}_1$（成比例），不要与"向量相等"混淆。

> 用行列式判定线性相关性，**只适用于方阵**（向量个数等于维数）。

> - $n$ 维空间中**最多有 $n$ 个**线性无关的向量
> - 超过 $n$ 个向量**一定**线性相关
> - 等于 $n$ 个向量时需具体判断

---

## 八、知识框架

```
向量组线性相关性
├── 线性组合：k₁α₁ + k₂α₂ + ⋯ + kₛαₛ
├── 线性表示：β = k₁α₁ + k₂α₂ + ⋯ + kₛαₛ
│   └── 判定：r(A) = r(A|β)
├── 线性相关：存在不全为零的系数使和为0
│   └── 判定：r(A) < s 或 |A| = 0（方阵时）
└── 线性无关：只有全零系数才能使和为0
    └── 判定：r(A) = s 或 |A| ≠ 0（方阵时）
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 11：极大线性无关组与向量组的秩]] — 无关组
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 12：等价向量组]] — 等价向量组
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 14：齐次线性方程组]] — 方程组
