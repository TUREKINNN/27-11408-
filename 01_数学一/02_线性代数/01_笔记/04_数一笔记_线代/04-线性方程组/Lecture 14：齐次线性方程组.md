---
title: "Lecture 14：齐次线性方程组"
subject: 线性代数
chapter: 04-线性方程组
difficulty: medium
exam_focus: true
created: 2026-06-16
---

# Lecture 14：齐次线性方程组

## 一、齐次线性方程组的基本形式

### 1.1 方程形式

$$\begin{cases} a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = 0 \\ a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = 0 \\ \vdots \\ a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = 0 \end{cases}$$

### 1.2 矩阵形式

$$Ax = \boldsymbol{0}$$

其中 $A = (a_{ij})_{m \times n}$ 为**系数矩阵**，$x = (x_1, x_2, \cdots, x_n)^T$。

> 右端常数项全为零，因此**一定有解**（$x_1 = x_2 = \cdots = x_n = 0$ 即**零解**/平凡解）。
> 核心问题是：**是否有非零解（非平凡解）？**

---

## 二、有非零解的条件

### 2.1 核心定理

> 设 $A$ 为 $m \times n$ 矩阵，齐次方程组 $Ax = 0$ 有非零解的**充要条件**是：
> $$\boxed{r(A) < n}$$
> 即系数矩阵的秩**小于**未知数的个数。

等价表述：
- 有非零解 $\iff r(A) < n$
- **只有零解**（唯一解）$\iff r(A) = n$

### 2.2 特殊情况

> 1. 当 $m < n$（方程个数 < 未知数个数）时，$r(A) \leq m < n$，**一定有非零解**
> 2. 当 $m = n$（方阵）时，有非零解 $\iff |A| = 0$
> 3. 当 $m = n$ 且 $|A| \neq 0$ 时，只有零解

---

## 三、基础解系

### 3.1 定义

> 设 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_t$ 是齐次方程组 $Ax = 0$ 的解向量，若满足：
> 1. $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_t$ **线性无关**
> 2. $Ax = 0$ 的**任意一个解**都能由 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_t$ 线性表示
>
> 则称 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_t$ 为 $Ax = 0$ 的一个**基础解系**。

### 3.2 基础解系的向量个数

> 设 $A$ 为 $m \times n$ 矩阵，$r(A) = r < n$，则 $Ax = 0$ 的基础解系含
> $$\boxed{n - r(A)}$$
> 个线性无关的解向量。
>
> 即解空间的维数为 $n - r(A)$。

> 基础解系不唯一，但所含向量个数固定为 $n - r(A)$。

### 3.3 基础解系的求法

> 1. 对系数矩阵 $A$ 做**初等行变换**化为**行最简形**（或阶梯形）
> 2. 确定 $r(A)$，确定自由变量（共 $n - r(A)$ 个）
> 3. 每次令**一个自由变量为 1、其余自由变量为 0**，回代求出主变量
> 4. 得到 $n - r(A)$ 个解向量，即为基础解系

---

## 四、通解

### 4.1 通解公式

> $$\boxed{x = k_1\boldsymbol{\xi}_1 + k_2\boldsymbol{\xi}_2 + \cdots + k_{n-r}\boldsymbol{\xi}_{n-r}}$$
> 其中 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_{n-r}$ 是基础解系，$k_1, k_2, \cdots, k_{n-r}$ 为任意常数。

### 4.2 解的结构

```
齐次方程组 Ax = 0 的解
├── 零解（平凡解）：x = 0
├── 非零解（非平凡解）
│   ├── 基础解系：ξ₁, ξ₂, ..., ξ_{n-r}
│   └── 通解：x = k₁ξ₁ + k₂ξ₂ + ⋯ + k_{n-r}ξ_{n-r}
└── 解空间：N(A) = span{ξ₁, ξ₂, ..., ξ_{n-r}}
```

---

## 五、齐次方程组解的性质

### 5.1 叠加原理

> 设 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2$ 是 $Ax = 0$ 的解，则：
> 1. $\boldsymbol{\xi}_1 + \boldsymbol{\xi}_2$ 也是 $Ax = 0$ 的解
> 2. $k\boldsymbol{\xi}_1$（$k$ 为任意常数）也是 $Ax = 0$ 的解
> 3. $k_1\boldsymbol{\xi}_1 + k_2\boldsymbol{\xi}_2$ 也是 $Ax = 0$ 的解
>
> 一般地，$Ax = 0$ 的解的**任意线性组合**仍是 $Ax = 0$ 的解。

### 5.2 解空间

> $Ax = 0$ 的全部解构成一个**向量空间**（解空间/零空间），维数为 $n - r(A)$。
> 基础解系就是解空间的一组**基**。

---

## 六、典型例题

### 例1：求基础解系和通解

求 $Ax = 0$ 的基础解系和通解，其中

$$A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 4 & 6 & 8 \\ 1 & 1 & 2 & 3 \end{pmatrix}$$

**解**：

$$A \xrightarrow{r_2 - 2r_1, r_3 - r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 0 & 0 & 0 \\ 0 & -1 & -1 & -1 \end{pmatrix} \xrightarrow{r_2 \leftrightarrow r_3} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & -1 & -1 & -1 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$$\xrightarrow{r_2 \times (-1)} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \end{pmatrix} \xrightarrow{r_1 - 2r_2} \begin{pmatrix} 1 & 0 & 1 & 2 \\ 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = 2$，$n = 4$，自由变量个数 $= 4 - 2 = 2$。

主变量：$x_1, x_2$；自由变量：$x_3, x_4$。

方程组化简为：
$$\begin{cases} x_1 = -x_3 - 2x_4 \\ x_2 = -x_3 - x_4 \end{cases}$$

令 $x_3 = 1, x_4 = 0$：$\boldsymbol{\xi}_1 = (-1, -1, 1, 0)^T$

令 $x_3 = 0, x_4 = 1$：$\boldsymbol{\xi}_2 = (-2, -1, 0, 1)^T$

**基础解系**：$\boldsymbol{\xi}_1, \boldsymbol{\xi}_2$

**通解**：$x = k_1\boldsymbol{\xi}_1 + k_2\boldsymbol{\xi}_2 = k_1(-1, -1, 1, 0)^T + k_2(-2, -1, 0, 1)^T$（$k_1, k_2$ 为任意常数）

### 例2：方阵情况

问 $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 3 & 6 & 9 \end{pmatrix}$ 的 $Ax = 0$ 是否有非零解？

**解**：$A$ 的每一行都成比例，$r(A) = 1 < 3$，有非零解。

基础解系含 $3 - 1 = 2$ 个向量。

行最简形：$\begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$

$x_1 = -2x_2 - 3x_3$

$\boldsymbol{\xi}_1 = (-2, 1, 0)^T, \boldsymbol{\xi}_2 = (-3, 0, 1)^T$

### 例3：含参数讨论

设 $A = \begin{pmatrix} 1 & 1 & a \\ 1 & a & 1 \\ a & 1 & 1 \end{pmatrix}$，$Ax = 0$ 只有零解，求 $a$ 的范围。

**解**：$Ax = 0$ 只有零解 $\iff |A| \neq 0$

$$|A| = \begin{vmatrix} 1 & 1 & a \\ 1 & a & 1 \\ a & 1 & 1 \end{vmatrix} = (a+2)(1-a)^2$$

$|A| \neq 0 \iff a \neq -2$ 且 $a \neq 1$。

### 例4：基础解系的判定

设 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \boldsymbol{\xi}_3$ 是 $Ax = 0$ 的基础解系，下列哪些也是基础解系？

(1) $\boldsymbol{\xi}_1 + \boldsymbol{\xi}_2, \boldsymbol{\xi}_2 + \boldsymbol{\xi}_3, \boldsymbol{\xi}_3 + \boldsymbol{\xi}_1$

(2) $\boldsymbol{\xi}_1, \boldsymbol{\xi}_1 + \boldsymbol{\xi}_2, \boldsymbol{\xi}_1 + \boldsymbol{\xi}_2 + \boldsymbol{\xi}_3$

**解**：需要验证：① 都是解 ② 线性无关 ③ 个数正确

**(1)** 由解的叠加性，三个向量都是解。个数 = 3 = $n - r(A)$。

检查线性无关：$k_1(\boldsymbol{\xi}_1 + \boldsymbol{\xi}_2) + k_2(\boldsymbol{\xi}_2 + \boldsymbol{\xi}_3) + k_3(\boldsymbol{\xi}_3 + \boldsymbol{\xi}_1) = 0$

$(k_1 + k_3)\boldsymbol{\xi}_1 + (k_1 + k_2)\boldsymbol{\xi}_2 + (k_2 + k_3)\boldsymbol{\xi}_3 = 0$

由 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \boldsymbol{\xi}_3$ 线性无关：$k_1 + k_3 = 0, k_1 + k_2 = 0, k_2 + k_3 = 0$

系数矩阵 $\begin{pmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$，$|·| = 2 \neq 0$，只有零解，线性无关。✓ 是基础解系。

**(2)** 个数 = 3，都是解。线性无关性由系数矩阵 $\begin{pmatrix} 1 & 1 & 1 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}$（上三角，对角元全 1）判定，$|·| = 1 \neq 0$，线性无关。✓ 是基础解系。

---

## 七、易错点总结

> 基础解系含 **$n - r(A)$** 个向量，不是 $m - r(A)$ 个！$n$ 是未知数个数。

> 仅仅是解的线性组合不一定构成基础解系，必须验证**线性无关**。

> 行最简形中**非主元列**对应的变量是自由变量。不要随便选自由变量。

> 齐次方程组一定有零解。"只有零解"意味着 $r(A) = n$，"有非零解"意味着 $r(A) < n$。

> $\dim(N(A)) = n - r(A)$，其中 $n$ 是列数（未知数个数），不是行数。

---

## 八、知识框架

```
齐次方程组 Ax = 0
├── 解的存在性
│   ├── 一定有零解
│   ├── 有非零解 ⟺ r(A) < n
│   └── 只有零解 ⟺ r(A) = n
├── 基础解系
│   ├── 个数：n - r(A)
│   ├── 求法：行变换 → 自由变量取单位向量
│   └── 就是解空间的基
├── 通解：x = k₁ξ₁ + k₂ξ₂ + ⋯ + k_{n-r}ξ_{n-r}
└── 解的性质
    ├── 解的线性组合仍是解
    └── 解空间是向量空间
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 15：非齐次线性方程组]] — 非齐次
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 9：矩阵的秩]] — 秩
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 10：向量与向量组的线性相关性]] — 向量
