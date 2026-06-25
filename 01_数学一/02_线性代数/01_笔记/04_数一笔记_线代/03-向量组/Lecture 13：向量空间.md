---
title: "Lecture 13：向量空间"
subject: 线性代数
chapter: 03-向量组
difficulty: hard
exam_focus: true
created: 2026-06-16
---

# Lecture 13：向量空间

## 一、向量空间的概念

### 1.1 定义

> 设 $V$ 是 $n$ 维向量的非空集合，若 $V$ 对向量的**加法**和**数乘**两种运算封闭，即：
> 1. $\forall \boldsymbol{\alpha}, \boldsymbol{\beta} \in V$，有 $\boldsymbol{\alpha} + \boldsymbol{\beta} \in V$
> 2. $\forall \boldsymbol{\alpha} \in V$，$\forall k \in \mathbb{R}$，有 $k\boldsymbol{\alpha} \in V$
>
> 则称 $V$ 是一个**向量空间**（或线性空间）。

### 1.2 常见的向量空间

| 向量空间 | 记号 | 说明 |
|----------|------|------|
| $n$ 维实向量空间 | $\mathbb{R}^n$ | 所有 $n$ 维实向量 |
| 零空间 | $\{\boldsymbol{0}\}$ | 只含零向量（最小的向量空间） |
| $Ax = 0$ 的解空间 | $N(A)$ | 齐次方程组的全部解 |
| 列空间 | $R(A) = C(A)$ | $A$ 的列向量组的线性组合全体 |
| 行空间 | $R(A^T)$ | $A$ 的行向量组的线性组合全体 |

> 齐次方程组 $Ax = 0$ 的解集是向量空间（称为**解空间**或**零空间**）。
> 非齐次方程组 $Ax = b$（$b \neq 0$）的解集**不是**向量空间（不含零向量）。

---

## 二、基、维数与坐标

### 2.1 基与维数

> 设 $V$ 是向量空间，若 $V$ 中存在 $r$ 个向量 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 满足：
> 1. $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ **线性无关**
> 2. $V$ 中**任意向量**都能由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 线性表示
>
> 则称 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 为 $V$ 的一组**基**（基底），$r$ 称为 $V$ 的**维数**，记为 $\dim(V) = r$。

> - 零空间 $\{\boldsymbol{0}\}$ 的维数为 0
> - $\mathbb{R}^n$ 的维数为 $n$
> - 基不唯一，但维数唯一

### 2.2 坐标

> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 是向量空间 $V$ 的一组基，$\forall \boldsymbol{\beta} \in V$，有唯一的表示：
> $$\boldsymbol{\beta} = x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + \cdots + x_n\boldsymbol{\alpha}_n$$
> 则称 $(x_1, x_2, \cdots, x_n)^T$ 为 $\boldsymbol{\beta}$ 在基 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 下的**坐标**。

> 因为基是线性无关的，所以坐标表示是**唯一**的。

### 2.3 求坐标的方法

设 $A = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n)$（以基为列构成方阵），则

$$\boldsymbol{\beta} = A\boldsymbol{x} \quad \Rightarrow \quad \boldsymbol{x} = A^{-1}\boldsymbol{\beta}$$

即解线性方程组 $x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + \cdots + x_n\boldsymbol{\alpha}_n = \boldsymbol{\beta}$。

---

## 三、基变换与坐标变换

### 3.1 过渡矩阵

> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 和 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_n$ 是 $\mathbb{R}^n$ 的两组基，且
> $$(\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_n) = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n)P$$
> 则称矩阵 $P$ 为从基 $\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n$ 到基 $\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n$ 的**过渡矩阵**。

> 过渡矩阵 $P$ 一定是**可逆矩阵**。

### 3.2 基变换公式

设旧基为 $(\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n)$，新基为 $(\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n)$，过渡矩阵为 $P$：

$$\boxed{(\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n) = (\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n)P}$$

### 3.3 坐标变换公式

> 设向量 $\boldsymbol{\gamma}$ 在旧基 $\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n$ 下的坐标为 $\boldsymbol{x}$，在新基 $\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n$ 下的坐标为 $\boldsymbol{y}$，则：
> $$\boxed{\boldsymbol{x} = P\boldsymbol{y}} \quad \text{或等价地} \quad \boxed{\boldsymbol{y} = P^{-1}\boldsymbol{x}}$$
> 其中 $P$ 是从旧基到新基的过渡矩阵。

**推导**：

$$\boldsymbol{\gamma} = (\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n)\boldsymbol{x} = (\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n)\boldsymbol{y} = (\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n)P\boldsymbol{y}$$

由坐标的唯一性，$\boldsymbol{x} = P\boldsymbol{y}$。

---

## 四、施密特正交化（Gram-Schmidt 正交化）

### 4.1 目的

将一组线性无关的向量 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 化为**正交向量组** $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_r$，使得它们**等价**（张成相同的子空间）。

### 4.2 施密特正交化公式

>
> **Step 1**：$\boldsymbol{\beta}_1 = \boldsymbol{\alpha}_1$
>
> **Step 2**：$\boldsymbol{\beta}_2 = \boldsymbol{\alpha}_2 - \dfrac{(\boldsymbol{\alpha}_2, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1$
>
> **Step 3**：$\boldsymbol{\beta}_3 = \boldsymbol{\alpha}_3 - \dfrac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1 - \dfrac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_2)}{(\boldsymbol{\beta}_2, \boldsymbol{\beta}_2)}\boldsymbol{\beta}_2$
>
> **一般公式**：
> $$\boxed{\boldsymbol{\beta}_k = \boldsymbol{\alpha}_k - \sum_{i=1}^{k-1}\frac{(\boldsymbol{\alpha}_k, \boldsymbol{\beta}_i)}{(\boldsymbol{\beta}_i, \boldsymbol{\beta}_i)}\boldsymbol{\beta}_i \quad (k = 1, 2, \cdots, r)}$$

其中 $(\boldsymbol{\alpha}, \boldsymbol{\beta}) = \boldsymbol{\alpha}^T\boldsymbol{\beta}$ 为内积（点积）。

### 4.3 单位化（规范化）

将正交向量组 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_r$ 单位化：

$$\boldsymbol{e}_i = \frac{\boldsymbol{\beta}_i}{\|\boldsymbol{\beta}_i\|} = \frac{\boldsymbol{\beta}_i}{\sqrt{(\boldsymbol{\beta}_i, \boldsymbol{\beta}_i)}} \quad (i = 1, 2, \cdots, r)$$

得到**标准正交向量组**（规范正交基）$\boldsymbol{e}_1, \boldsymbol{e}_2, \cdots, \boldsymbol{e}_r$。

### 4.4 性质

1. $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_r$ 是**正交向量组**：$(\boldsymbol{\beta}_i, \boldsymbol{\beta}_j) = 0$（$i \neq j$）
2. $\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_k$ 与 $\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_k$ 等价（$k = 1, 2, \cdots, r$）
3. 正交向量组一定**线性无关**

---

## 五、标准正交基

### 5.1 定义

> 设 $\boldsymbol{e}_1, \boldsymbol{e}_2, \cdots, \boldsymbol{e}_n$ 是 $n$ 维向量空间 $V$ 的一组基，若满足：
> $$(\boldsymbol{e}_i, \boldsymbol{e}_j) = \begin{cases} 1, & i = j \\ 0, & i \neq j \end{cases}$$
> 则称 $\boldsymbol{e}_1, \boldsymbol{e}_2, \cdots, \boldsymbol{e}_n$ 为 $V$ 的一组**标准正交基**（规范正交基）。

### 5.2 标准正交基下坐标的求法

> 若 $\boldsymbol{e}_1, \boldsymbol{e}_2, \cdots, \boldsymbol{e}_n$ 是标准正交基，则 $\boldsymbol{\beta}$ 在该基下的坐标为：
> $$\boldsymbol{x} = \begin{pmatrix} (\boldsymbol{\beta}, \boldsymbol{e}_1) \\ (\boldsymbol{\beta}, \boldsymbol{\e}_2) \\ \vdots \\ (\boldsymbol{\beta}, \boldsymbol{e}_n) \end{pmatrix}$$
> 即坐标 = 向量与各基向量的内积。

---

## 六、解空间（齐次方程组的解空间）

### 6.1 解空间的基

齐次方程组 $Ax = 0$ 的解空间 $N(A)$ 的维数：

$$\dim(N(A)) = n - r(A)$$

其中 $n$ 为未知数个数，$r(A)$ 为系数矩阵的秩。

解空间的基就是**基础解系**。

### 6.2 列空间与行空间

- 列空间 $R(A)$：$A$ 的列向量组的线性组合全体，$\dim(R(A)) = r(A)$
- 行空间 $R(A^T)$：$A$ 的行向量组的线性组合全体，$\dim(R(A^T)) = r(A)$

> $$\dim(R(A)) + \dim(N(A)) = n$$
> 即 $r(A) + (n - r(A)) = n$

---

## 七、典型例题

### 例1：求过渡矩阵

$\mathbb{R}^3$ 中，旧基 $\boldsymbol{\alpha}_1 = (1, 0, 0)^T, \boldsymbol{\alpha}_2 = (0, 1, 0)^T, \boldsymbol{\alpha}_3 = (0, 0, 1)^T$（标准基），新基 $\boldsymbol{\beta}_1 = (1, 1, 0)^T, \boldsymbol{\beta}_2 = (1, 0, 1)^T, \boldsymbol{\beta}_3 = (0, 1, 1)^T$。求过渡矩阵。

**解**：

$$(\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \boldsymbol{\beta}_3) = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3)P$$

因为 $(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3) = I$（标准基），所以

$$P = (\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \boldsymbol{\beta}_3) = \begin{pmatrix} 1 & 1 & 0 \\ 1 & 0 & 1 \\ 0 & 1 & 1 \end{pmatrix}$$

### 例2：坐标变换

$\mathbb{R}^2$ 中，旧基 $\boldsymbol{\alpha}_1 = (1, 0)^T, \boldsymbol{\alpha}_2 = (0, 1)^T$，新基 $\boldsymbol{\beta}_1 = (1, 1)^T, \boldsymbol{\beta}_2 = (1, -1)^T$。向量 $\boldsymbol{\gamma}$ 在旧基下的坐标为 $(3, 2)^T$，求在新基下的坐标。

**解**：

$$P = \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}, \quad \boldsymbol{x} = \begin{pmatrix} 3 \\ 2 \end{pmatrix}$$

$$\boldsymbol{y} = P^{-1}\boldsymbol{x} = \frac{1}{-2}\begin{pmatrix} -1 & -1 \\ -1 & 1 \end{pmatrix}\begin{pmatrix} 3 \\ 2 \end{pmatrix} = \begin{pmatrix} 1/2 & 1/2 \\ 1/2 & -1/2 \end{pmatrix}\begin{pmatrix} 3 \\ 2 \end{pmatrix} = \begin{pmatrix} 5/2 \\ 1/2 \end{pmatrix}$$

### 例3：施密特正交化

将 $\boldsymbol{\alpha}_1 = (1, 1, 0)^T, \boldsymbol{\alpha}_2 = (1, 0, 1)^T, \boldsymbol{\alpha}_3 = (0, 1, 1)^T$ 正交化。

**解**：

$$\boldsymbol{\beta}_1 = \boldsymbol{\alpha}_1 = (1, 1, 0)^T$$

$$\boldsymbol{\beta}_2 = \boldsymbol{\alpha}_2 - \frac{(\boldsymbol{\alpha}_2, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1 = (1, 0, 1)^T - \frac{1}{2}(1, 1, 0)^T = \left(\frac{1}{2}, -\frac{1}{2}, 1\right)^T$$

$$\boldsymbol{\beta}_3 = \boldsymbol{\alpha}_3 - \frac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1 - \frac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_2)}{(\boldsymbol{\beta}_2, \boldsymbol{\beta}_2)}\boldsymbol{\beta}_2$$

$$= (0, 1, 1)^T - \frac{1}{2}(1, 1, 0)^T - \frac{1/2}{3/2}\left(\frac{1}{2}, -\frac{1}{2}, 1\right)^T$$

$$= (0, 1, 1)^T - \left(\frac{1}{2}, \frac{1}{2}, 0\right)^T - \frac{1}{3}\left(\frac{1}{2}, -\frac{1}{2}, 1\right)^T = \left(-\frac{2}{3}, \frac{2}{3}, \frac{2}{3}\right)^T$$

**验证**：$(\boldsymbol{\beta}_1, \boldsymbol{\beta}_2) = 1/2 - 1/2 = 0$ ✓，$(\boldsymbol{\beta}_1, \boldsymbol{\beta}_3) = -2/3 + 2/3 = 0$ ✓，$(\boldsymbol{\beta}_2, \boldsymbol{\beta}_3) = -1/3 - 1/3 + 2/3 = 0$ ✓

### 例4：求解空间的基与维数

求 $A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 3 & 4 & 5 \\ 3 & 5 & 7 & 9 \end{pmatrix}$ 的零空间的基和维数。

**解**：

$$A \xrightarrow{r_2 - 2r_1, r_3 - 3r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -2 & -3 \\ 0 & -1 & -2 & -3 \end{pmatrix} \xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -2 & -3 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 2$，$\dim(N(A)) = 4 - 2 = 2$。

回代：$-x_2 - 2x_3 - 3x_4 = 0 \Rightarrow x_2 = -2x_3 - 3x_4$

$x_1 = -2x_2 - 3x_3 - 4x_4 = -2(-2x_3 - 3x_4) - 3x_3 - 4x_4 = x_3 + 2x_4$

令 $x_3 = 1, x_4 = 0$：$\boldsymbol{\xi}_1 = (1, -2, 1, 0)^T$

令 $x_3 = 0, x_4 = 1$：$\boldsymbol{\xi}_2 = (2, -3, 0, 1)^T$

基础解系（零空间的基）为 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2$。

---

## 八、易错点总结

> 坐标 $(x_1, x_2, \cdots, x_n)^T$ 是**列向量**，不要写成行向量。

> $(\boldsymbol{\beta}_1, \cdots, \boldsymbol{\beta}_n) = (\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n)P$ 中 $P$ 是从旧基到新基的过渡矩阵。
> 坐标变换是 $\boldsymbol{x} = P\boldsymbol{y}$（旧坐标 = 过渡矩阵 × 新坐标），不要弄反。

> 正交化后的新向量组与原向量组**等价**，张成相同的子空间。

> 解空间的维数是 $n - r(A)$（未知数个数减秩），不是 $m - r(A)$。

---

## 九、知识框架

```
向量空间
├── 定义：对加法和数乘封闭
├── 基与维数
│   ├── 基：极大无关组（线性无关 + 张成整个空间）
│   ├── 维数：基中向量个数
│   └── 坐标：向量在基下的分解系数
├── 基变换与坐标变换
│   ├── 过渡矩阵 P
│   ├── 基变换：B = AP
│   └── 坐标变换：x = Py
├── 施密特正交化
│   ├── 逐步减去在已有方向上的投影
│   └── 产生等价的正交向量组
└── 解空间
    ├── dim = n - r(A)
    └── 基 = 基础解系
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 10：向量与向量组的线性相关性]] — 向量
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 11：极大线性无关组与向量组的秩]] — 无关组
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/05-特征值与特征向量/Lecture 19：相似]] — 相似
