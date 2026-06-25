---
title: Lecture 7：矩阵方程
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 7：矩阵方程

## 一、矩阵方程的基本类型

矩阵方程是考研线性代数的常见题型，主要有以下三种基本形式：

> [!definition|purple] 三种基本矩阵方程
> 1. **$AX = B$**：左乘型
> 2. **$XA = B$**：右乘型
> 3. **$AXB = C$**：双边型

---

## 二、$AX = B$ 型

### 2.1 解法

> [!theorem|blue] $AX = B$ 的解法
> 若 $A$ 可逆，则 $X = A^{-1}B$。
>
> **计算方法：** $(A | B) \xrightarrow{\text{初等行变换}} (I | A^{-1}B) = (I | X)$

**原理：** 将 $B$ 视为多个列向量，对 $(A|B)$ 做初等行变换化 $A$ 为 $I$ 的过程，就是同时对 $B$ 左乘 $A^{-1}$ 的过程。

### 经典例题

**例1：** 解矩阵方程 $AX = B$，其中
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 3 & 7 & 9 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ 0 & 1 \\ 1 & 1 \end{pmatrix}
$$

**解：**

$$
(A | B) = \left(\begin{array}{ccc|cc} 1 & 2 & 3 & 1 & 0 \\ 2 & 5 & 7 & 0 & 1 \\ 3 & 7 & 9 & 1 & 1 \end{array}\right)
$$

$r_2 - 2r_1, r_3 - 3r_1$：
$$
\rightarrow \left(\begin{array}{ccc|cc} 1 & 2 & 3 & 1 & 0 \\ 0 & 1 & 1 & -2 & 1 \\ 0 & 1 & 0 & -2 & 1 \end{array}\right)
$$

$r_3 - r_2$：
$$
\rightarrow \left(\begin{array}{ccc|cc} 1 & 2 & 3 & 1 & 0 \\ 0 & 1 & 1 & -2 & 1 \\ 0 & 0 & -1 & 0 & 0 \end{array}\right)
$$

$r_3 \times (-1)$：
$$
\rightarrow \left(\begin{array}{ccc|cc} 1 & 2 & 3 & 1 & 0 \\ 0 & 1 & 1 & -2 & 1 \\ 0 & 0 & 1 & 0 & 0 \end{array}\right)
$$

$r_2 - r_3, r_1 - 3r_3$：
$$
\rightarrow \left(\begin{array}{ccc|cc} 1 & 2 & 0 & 1 & 0 \\ 0 & 1 & 0 & -2 & 1 \\ 0 & 0 & 1 & 0 & 0 \end{array}\right)
$$

$r_1 - 2r_2$：
$$
\rightarrow \left(\begin{array}{ccc|cc} 1 & 0 & 0 & 5 & -2 \\ 0 & 1 & 0 & -2 & 1 \\ 0 & 0 & 1 & 0 & 0 \end{array}\right)
$$

$$
X = \begin{pmatrix} 5 & -2 \\ -2 & 1 \\ 0 & 0 \end{pmatrix}
$$

---

## 三、$XA = B$ 型

### 3.1 解法

> [!theorem|blue] $XA = B$ 的解法
> 若 $A$ 可逆，则 $X = BA^{-1}$。
>
> **方法1：** 转化为 $A^T X^T = B^T$，用 $AX=B$ 型的方法求 $X^T$，再转置。
>
> **方法2：** 对 $\begin{pmatrix} A \\ B \end{pmatrix}$ 做初等**列**变换：$\begin{pmatrix} A \\ B \end{pmatrix} \xrightarrow{\text{列变换}} \begin{pmatrix} I \\ BA^{-1} \end{pmatrix} = \begin{pmatrix} I \\ X \end{pmatrix}$

### 经典例题

**例2：** 解矩阵方程 $XA = B$，其中
$$
A = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ 0 & 1 \\ -1 & 0 \end{pmatrix}
$$

**解（方法1）：** 转置 $A^T X^T = B^T$

$$
A^T = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix}, \quad B^T = \begin{pmatrix} 1 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix}
$$

$$
(A^T | B^T) = \left(\begin{array}{cc|ccc} 1 & 1 & 1 & 0 & -1 \\ 1 & 2 & 0 & 1 & 0 \end{array}\right)
$$

$r_2 - r_1$：
$$
\rightarrow \left(\begin{array}{cc|ccc} 1 & 1 & 1 & 0 & -1 \\ 0 & 1 & -1 & 1 & 1 \end{array}\right)
$$

$r_1 - r_2$：
$$
\rightarrow \left(\begin{array}{cc|ccc} 1 & 0 & 2 & -1 & -2 \\ 0 & 1 & -1 & 1 & 1 \end{array}\right)
$$

$$
X^T = \begin{pmatrix} 2 & -1 & -2 \\ -1 & 1 & 1 \end{pmatrix}, \quad X = \begin{pmatrix} 2 & -1 \\ -1 & 1 \\ -2 & 1 \end{pmatrix}
$$

---

## 四、$AXB = C$ 型

### 4.1 解法

> [!theorem|blue] $AXB = C$ 的解法
> 若 $A, B$ 都可逆，则 $X = A^{-1}CB^{-1}$。
>
> **分步计算：**
> 1. 先解 $AY = C$ 得 $Y = A^{-1}C$
> 2. 再解 $XB = Y$ 得 $X = YB^{-1} = A^{-1}CB^{-1}$

### 经典例题

**例3：** 解矩阵方程 $AXB = C$，其中
$$
A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}, \quad B = \begin{pmatrix} 2 & 1 \\ 5 & 3 \end{pmatrix}, \quad C = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
$$

**解：**

第一步：解 $AY = C$，即 $Y = A^{-1}$

$$
(A | I) = \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array}\right) \xrightarrow{r_2 - 3r_1} \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array}\right)
$$

$$
\xrightarrow{r_2 \times (-1)} \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array}\right) \xrightarrow{r_1 - 2r_2} \left(\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array}\right)
$$

$$
Y = A^{-1} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix}
$$

第二步：解 $X B = Y$，即 $X = YB^{-1}$

$$
(B^T | Y^T) = \left(\begin{array}{cc|cc} 2 & 5 & -5 & 3 \\ 1 & 3 & 2 & -1 \end{array}\right) \xrightarrow{r_1 \leftrightarrow r_2} \left(\begin{array}{cc|cc} 1 & 3 & 2 & -1 \\ 2 & 5 & -5 & 3 \end{array}\right)
$$

$$
\xrightarrow{r_2 - 2r_1} \left(\begin{array}{cc|cc} 1 & 3 & 2 & -1 \\ 0 & -1 & -9 & 5 \end{array}\right) \xrightarrow{r_2 \times (-1)} \left(\begin{array}{cc|cc} 1 & 3 & 2 & -1 \\ 0 & 1 & 9 & -5 \end{array}\right)
$$

$$
\xrightarrow{r_1 - 3r_2} \left(\begin{array}{cc|cc} 1 & 0 & -25 & 14 \\ 0 & 1 & 9 & -5 \end{array}\right)
$$

$$
X^T = \begin{pmatrix} -25 & 14 \\ 9 & -5 \end{pmatrix}, \quad X = \begin{pmatrix} -25 & 9 \\ 14 & -5 \end{pmatrix}
$$

---

## 五、$A$ 不可逆时的矩阵方程

当 $|A| = 0$ 时，$A$ 不可逆，不能直接用 $A^{-1}$。此时需要通过方程组来分析。

> [!definition|purple] $AX = B$ 有解的条件
> $AX = B$ 有解 $\Leftrightarrow$ $r(A) = r(A|B)$
>
> - 若 $r(A) = r(A|B) = n$（$n$ 为 $A$ 的列数），则有**唯一解**
> - 若 $r(A) = r(A|B) < n$，则有**无穷多解**
> - 若 $r(A) \neq r(A|B)$，则**无解**

**例4：** 讨论矩阵方程 $AX = B$ 的解，其中
$$
A = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 \\ 1 \end{pmatrix}
$$

**解：** $|A| = 0$，$A$ 不可逆。

$$
(A|B) = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \end{pmatrix} \xrightarrow{r_2 - r_1} \begin{pmatrix} 1 & 1 & 1 \\ 0 & 0 & 0 \end{pmatrix}
$$

$r(A) = r(A|B) = 1 < 2$，有无穷多解。

$X = \begin{pmatrix} 1-t \\ t \end{pmatrix}$（$t$ 为任意常数）

---

## 六、矩阵方程的常见变形

### 6.1 含 $A^*$ 的方程

**例5：** 设 $A^* X = A^{-1}B + 2X$，其中 $A = \begin{pmatrix} 1 & 1 & -1 \\ -1 & 1 & 1 \\ 1 & -1 & 1 \end{pmatrix}$，$B = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}$，求 $X$。

**解：** 由 $A^* = |A|A^{-1}$，先求 $|A|$：

$$
|A| = 1(1+1) - 1(-1-1) + (-1)(1-1) = 2 + 2 + 0 = 4
$$

方程变为 $4A^{-1}X = A^{-1}B + 2X$

两边左乘 $A$：$4X = B + 2AX$

$(4I - 2A)X = B$

$$
4I - 2A = \begin{pmatrix} 4-2 & -2 & 2 \\ 2 & 4-2 & -2 \\ -2 & 2 & 4-2 \end{pmatrix} = \begin{pmatrix} 2 & -2 & 2 \\ 2 & 2 & -2 \\ -2 & 2 & 2 \end{pmatrix}
$$

解 $(4I-2A)X = B$，用初等行变换求解。

### 6.2 含幂的方程

**例6：** 设 $A = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} + \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix} = I + N$，解方程 $A^2 X = A$。

**解：** $A = I + N$，$N^3 = O$。

$A^2 = (I+N)^2 = I + 2N + N^2$

方程：$(I + 2N + N^2)X = I + N$

$$
X = (I + 2N + N^2)^{-1}(I + N)
$$

---

## 七、易错点总结

> [!warning|red] 常见错误清单
> 1. **$AX=B$ 解为 $X=A^{-1}B$**：不是 $BA^{-1}$，顺序不能错
> 2. **$XA=B$ 解为 $X=BA^{-1}$**：不是 $A^{-1}B$
> 3. **先判断 $A$ 是否可逆**：$|A| = 0$ 时不能直接用逆矩阵
> 4. **初等行变换法**：$(A|B) \to (I|X)$，不能混用列变换
> 5. **矩阵方程解的结构**：不可逆时要用方程组理论
> 6. **含 $A^*$ 的方程**：先将 $A^*$ 转化为 $|A|A^{-1}$
> 7. **$AXB = C$ 分两步**：先解 $AY = C$，再解 $Y = XB$
> 8. **验证答案**：将求得的 $X$ 代入原方程验证

---

## 八、本讲小结

| 方程类型 | 解法 | 条件 |
|---------|------|------|
| $AX = B$ | $X = A^{-1}B$ | $\|A\| \neq 0$ |
| $XA = B$ | $X = BA^{-1}$ | $\|A\| \neq 0$ |
| $AXB = C$ | $X = A^{-1}CB^{-1}$ | $\|A\| \neq 0$ 且 $\|B\| \neq 0$ |

> [!tip|blue] 考研重点
> 矩阵方程是线性代数计算题的核心题型。关键是分清方程类型、判断可逆性、选择正确的求解顺序。含伴随矩阵的方程是高频考点，需要熟练掌握 $A^* = |A|A^{-1}$ 的转化技巧。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 6：初等变换与初等矩阵]] — 初等变换
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 4：矩阵的逆]] — 逆矩阵
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 15：非齐次线性方程组]] — 方程组
