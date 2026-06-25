---
title: "Lecture 15：非齐次线性方程组"
subject: 线性代数
chapter: 04-线性方程组
difficulty: medium
exam_focus: true
created: 2026-06-16
---

# Lecture 15：非齐次线性方程组

## 一、非齐次线性方程组的基本形式

### 1.1 方程形式

$$\begin{cases} a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\ a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\ \vdots \\ a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m \end{cases}$$

### 1.2 矩阵形式

$$Ax = b$$

其中 $A = (a_{ij})_{m \times n}$ 为系数矩阵，$b = (b_1, b_2, \cdots, b_m)^T \neq \boldsymbol{0}$。

**增广矩阵**：$\bar{A} = (A | b)$

---

## 二、有解条件

### 2.1 核心定理

>
> **有解**（相容）$\iff$ $\boxed{r(A) = r(\bar{A})}$
>
> - 有**唯一解** $\iff r(A) = r(\bar{A}) = n$
> - 有**无穷多解** $\iff r(A) = r(\bar{A}) < n$
> - **无解**（不相容）$\iff r(A) \neq r(\bar{A})$，即 $r(A) < r(\bar{A})$

### 2.2 三种情况总结

| 条件 | 结论 | 解的情况 |
|------|------|----------|
| $r(A) = r(\bar{A}) = n$ | 有解 | **唯一解** |
| $r(A) = r(\bar{A}) < n$ | 有解 | **无穷多解** |
| $r(A) \neq r(\bar{A})$ | 无解 | 不相容 |

> $r(A) < r(\bar{A})$，即增广矩阵的秩比系数矩阵的秩**大 1**（因为加一列秩最多增 1）。
> 几何上，这意味着存在"矛盾方程"。

---

## 三、解的结构

### 3.1 通解定理

> 设 $\boldsymbol{\eta}^*$ 是非齐次方程组 $Ax = b$ 的一个**特解**（某个具体的解），
> $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_{n-r}$ 是对应齐次方程组 $Ax = 0$ 的基础解系，
> 则 $Ax = b$ 的**通解**为：
>
> $$\boxed{x = \boldsymbol{\eta}^* + k_1\boldsymbol{\xi}_1 + k_2\boldsymbol{\xi}_2 + \cdots + k_{n-r}\boldsymbol{\xi}_{n-r}}$$
>
> 其中 $k_1, k_2, \cdots, k_{n-r}$ 为任意常数，$r = r(A)$。

> 非齐次通解的结构是：**一个特解** + **对应齐次方程组的通解**。
> 齐次部分 $\boldsymbol{\xi}_1, \cdots, \boldsymbol{\xi}_{n-r}$ 来自 $Ax = 0$，不是 $Ax = b$。

### 3.2 解的性质

> 1. $Ax = b$ 的**两个解之差**是 $Ax = 0$ 的解
>    - 即 $\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2$ 满足 $A(\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2) = \boldsymbol{0}$
> 2. $Ax = b$ 的**一个解**加上 $Ax = 0$ 的**一个解**仍是 $Ax = b$ 的解
>    - 即 $\boldsymbol{\eta}^* + \boldsymbol{\xi}$ 满足 $A(\boldsymbol{\eta}^* + \boldsymbol{\xi}) = b$
> 3. $Ax = b$ 的两个解的**线性组合**一般不是 $Ax = b$ 的解
>    - 除非系数之和为 1：$k_1 + k_2 = 1$ 时，$k_1\boldsymbol{\eta}_1 + k_2\boldsymbol{\eta}_2$ 是 $Ax = b$ 的解

---

## 四、求解方法

### 4.1 高斯消元法

> 1. 写出增广矩阵 $\bar{A} = (A | b)$
> 2. 对 $\bar{A}$ 做**初等行变换**化为行阶梯形（或行最简形）
> 3. 判断 $r(A)$ 与 $r(\bar{A})$
>    - $r(A) \neq r(\bar{A})$：无解
>    - $r(A) = r(\bar{A})$：有解，继续求解
> 4. 回代求解
>    - $r(A) = r(\bar{A}) = n$：唯一解
>    - $r(A) = r(\bar{A}) < n$：令自由变量为零得**特解** $\boldsymbol{\eta}^*$；令自由变量取单位向量得**基础解系** $\boldsymbol{\xi}_1, \cdots, \boldsymbol{\xi}_{n-r}$

### 4.2 特解的取法

> 在行最简形中，令**所有自由变量 = 0**，解出主变量的值，得到的解就是特解 $\boldsymbol{\eta}^*$。
>
> 也可以将右边常数项视为一个自由变量为 0 的特殊情况。

---

## 五、典型例题

### 例1：判断解的情况并求通解

$$\begin{cases} x_1 + 2x_2 + 3x_3 = 4 \\ 2x_1 + 4x_2 + 5x_3 = 6 \\ 3x_1 + 6x_2 + 8x_3 = 10 \end{cases}$$

**解**：

$$\bar{A} = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 4 & 5 & 6 \\ 3 & 6 & 8 & 10 \end{pmatrix} \xrightarrow{r_2 - 2r_1, r_3 - 3r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 0 & -1 & -2 \\ 0 & 0 & -1 & -2 \end{pmatrix}$$

$$\xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 0 & -1 & -2 \\ 0 & 0 & 0 & 0 \end{pmatrix}$$

$r(A) = r(\bar{A}) = 2 < 3$，有无穷多解。

行最简形：$\begin{pmatrix} 1 & 2 & 0 & -2 \\ 0 & 0 & 1 & 2 \\ 0 & 0 & 0 & 0 \end{pmatrix}$

方程组：$\begin{cases} x_1 + 2x_2 = -2 \\ x_3 = 2 \end{cases}$

**特解**：令 $x_2 = 0$，$\boldsymbol{\eta}^* = (-2, 0, 2)^T$

**基础解系**：令 $x_2 = 1$，$\boldsymbol{\xi} = (-2, 1, 0)^T$

**通解**：$x = (-2, 0, 2)^T + k(-2, 1, 0)^T$（$k$ 为任意常数）

### 例2：无解的情况

$$\begin{cases} x_1 + x_2 + x_3 = 1 \\ 2x_1 + 3x_2 + 4x_3 = 2 \\ 3x_1 + 4x_2 + 5x_3 = 4 \end{cases}$$

**解**：

$$\bar{A} = \begin{pmatrix} 1 & 1 & 1 & 1 \\ 2 & 3 & 4 & 2 \\ 3 & 4 & 5 & 4 \end{pmatrix} \xrightarrow{r_2 - 2r_1, r_3 - 3r_1} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & 2 & 0 \\ 0 & 1 & 2 & 1 \end{pmatrix}$$

$$\xrightarrow{r_3 - r_2} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & 2 & 0 \\ 0 & 0 & 0 & 1 \end{pmatrix}$$

$r(A) = 2$，$r(\bar{A}) = 3$，$r(A) \neq r(\bar{A})$，**无解**。

> 第三行 $0x_1 + 0x_2 + 0x_3 = 1$ 是矛盾方程。

### 例3：含参数讨论

设 $\begin{cases} x_1 + x_2 + \lambda x_3 = 1 \\ x_1 + \lambda x_2 + x_3 = \lambda \\ \lambda x_1 + x_2 + x_3 = \lambda^2 \end{cases}$，讨论 $\lambda$ 为何值时无解、有唯一解、有无穷多解。

**解**：

$$\bar{A} = \begin{pmatrix} 1 & 1 & \lambda & 1 \\ 1 & \lambda & 1 & \lambda \\ \lambda & 1 & 1 & \lambda^2 \end{pmatrix}$$

$$\xrightarrow{r_2 - r_1, r_3 - \lambda r_1} \begin{pmatrix} 1 & 1 & \lambda & 1 \\ 0 & \lambda - 1 & 1 - \lambda & \lambda - 1 \\ 0 & 1 - \lambda & 1 - \lambda^2 & \lambda^2 - \lambda \end{pmatrix}$$

$$\xrightarrow{r_3 + r_2} \begin{pmatrix} 1 & 1 & \lambda & 1 \\ 0 & \lambda - 1 & 1 - \lambda & \lambda - 1 \\ 0 & 0 & 2 - \lambda - \lambda^2 & \lambda^2 - 1 \end{pmatrix}$$

因式分解：$2 - \lambda - \lambda^2 = -(1+\lambda)(\lambda-2) = (2+\lambda)(1-\lambda)$

$\lambda^2 - 1 = (\lambda-1)(\lambda+1)$

**情况分析**：

**(1)** $\lambda \neq 1$ 且 $\lambda \neq -2$ 时：$r(A) = r(\bar{A}) = 3 = n$，**唯一解**。

**(2)** $\lambda = 1$ 时：第二、三行全零，$r(A) = r(\bar{A}) = 1 < 3$，**无穷多解**。

**(3)** $\lambda = -2$ 时：$r(A) = 2$，$r(\bar{A}) = 3$（第三行为 $0 = -3$），**无解**。

### 例4：非齐次通解的应用

设 $\boldsymbol{\eta}_1 = (1, 0, 2)^T, \boldsymbol{\eta}_2 = (0, 1, -1)^T$ 是 $Ax = b$ 的两个解，$r(A) = 1$，求 $Ax = b$ 的通解。

**解**：

$n = 3$，$r(A) = 1$，齐次方程组的基础解系含 $3 - 1 = 2$ 个向量。

$\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2 = (1, -1, 3)^T$ 是 $Ax = 0$ 的解。

但需要 2 个线性无关的齐次解，而我们只有一个差。需要更多信息。

等一下，$r(A) = 1$，$n = 3$，基础解系应含 2 个向量。但这里我们只有 $\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2$ 一个齐次解。

此题条件不足以确定完整的通解。但若 $A$ 是 $3 \times 3$ 矩阵，则 $Ax = 0$ 的基础解系含 2 个向量。只有一个差向量不够。

**修正**：此题实际只能给出通解的一个形式：

$x = \boldsymbol{\eta}_1 + k(\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2) = (1, 0, 2)^T + k(1, -1, 3)^T$

但这不是完整通解（缺一个齐次解方向）。需要更多信息。

> 求非齐次通解时，需要知道齐次方程组的**完整**基础解系，不能遗漏。

---

## 六、非齐次方程组的 Cramer 法则

### 6.1 定理

> 当 $r(A) = r(\bar{A}) = n$（方阵且 $|A| \neq 0$）时，唯一解为：
> $$x_i = \frac{|A_i|}{|A|} \quad (i = 1, 2, \cdots, n)$$
> 其中 $A_i$ 是将 $A$ 的第 $i$ 列替换为 $b$ 后得到的矩阵。

---

## 七、易错点总结

> 非齐次通解中的齐次部分来自 $Ax = 0$，不是 $Ax = b$。

> 判断有解要用增广矩阵的秩，不要只看系数矩阵。

> 不同的自由变量取值得到不同的特解，但通解相同。

> $\boldsymbol{\eta}_1 - \boldsymbol{\eta}_2$ 是 $Ax = 0$ 的解，但 $\boldsymbol{\eta}_1 + \boldsymbol{\eta}_2$ 不是 $Ax = b$ 的解（一般情况下）。

> $k_1\boldsymbol{\eta}_1 + k_2\boldsymbol{\eta}_2$ 是 $Ax = b$ 的解 $\iff k_1 + k_2 = 1$。

---

## 八、知识框架

```
非齐次方程组 Ax = b
├── 有解条件
│   ├── 有解 ⟺ r(A) = r(Ā)
│   ├── 唯一解 ⟺ r(A) = r(Ā) = n
│   ├── 无穷多解 ⟺ r(A) = r(Ā) < n
│   └── 无解 ⟺ r(A) < r(Ā)
├── 通解结构
│   ├── 特解 η*：令自由变量 = 0
│   ├── 齐次基础解系：ξ₁, ..., ξ_{n-r}
│   └── 通解 = η* + k₁ξ₁ + ⋯ + k_{n-r}ξ_{n-r}
└── 解的性质
    ├── 解之差 = 齐次解
    ├── 特解 + 齐次解 = 非齐次解
    └── 系数和为1的组合 = 非齐次解
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 14：齐次线性方程组]] — 齐次
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 16：两个方程组的公共解]] — 公共解
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 17：同解方程组]] — 同解
