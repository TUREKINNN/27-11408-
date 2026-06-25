---
title: Lecture 9：矩阵的秩
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 9：矩阵的秩

## 一、秩的定义

### 1.1 k阶子式

> [!definition|purple] k阶子式
> 在 $m \times n$ 矩阵 $A$ 中，任意选取 $k$ 行和 $k$ 列（$k \le \min(m,n)$），位于这些行和列交叉处的 $k^2$ 个元素按原来相对位置构成的 $k$ 阶行列式，称为 $A$ 的一个 **$k$ 阶子式**。

### 1.2 矩阵的秩

> [!definition|purple] 矩阵的秩
> 矩阵 $A$ 中**不等于零的子式的最高阶数**称为矩阵 $A$ 的**秩**，记为 $r(A)$。
>
> 规定零矩阵的秩为 $0$。

**等价定义：**
- $r(A)$ = $A$ 的行阶梯形中非零行的行数
- $r(A)$ = $A$ 的行向量组的秩（极大无关组的向量个数）
- $r(A)$ = $A$ 的列向量组的秩

**基本范围：**
$$
0 \le r(A_{m \times n}) \le \min(m, n)
$$

---

## 二、秩的计算方法

### 2.1 初等变换法（最常用）

> [!theorem|blue] 初等变换法求秩
> 初等变换不改变矩阵的秩。将矩阵通过初等行变换化为行阶梯形，非零行的个数即为秩。

**例1：** 求 $A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 5 & 7 & 9 \\ 3 & 7 & 10 & 13 \\ 1 & 3 & 4 & 5 \end{pmatrix}$ 的秩。

**解：**

$$
A \xrightarrow{r_2-2r_1, r_3-3r_1, r_4-r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & 1 \\ 0 & 1 & 1 & 1 \\ 0 & 1 & 1 & 1 \end{pmatrix} \xrightarrow{r_3-r_2, r_4-r_2} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix}
$$

$r(A) = 2$。

### 2.2 定义法（行列式法）

找最高阶非零子式。

**例2：** 设 $A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & -2 \\ 3 & 6 & -3 \end{pmatrix}$，求 $r(A)$。

**解：** 观察各行成比例（第2行 = 2×第1行，第3行 = 3×第1行）。

$|A| = 0$（三阶子式为零），$A$ 中有二阶子式 $\begin{vmatrix} 1 & 2 \\ 2 & 4 \end{vmatrix} = 0$。

但 $\begin{vmatrix} 1 & -1 \\ 2 & -2 \end{vmatrix} = 0$... 实际上所有二阶子式都为零（因为行成比例）。

一阶子式 $a_{11} = 1 \neq 0$，所以 $r(A) = 1$。

---

## 三、秩的性质

> [!theorem|blue] 矩阵秩的基本性质
> 1. $r(A) = r(A^T) = r(-A)$
> 2. $r(kA) = r(A)$（$k \neq 0$），$r(O) = 0$
> 3. $r(A+B) \le r(A) + r(B)$
> 4. $r(AB) \le \min(r(A), r(B))$
> 5. 若 $P$ 可逆，则 $r(PA) = r(A)$，$r(AQ) = r(A)$
> 6. $r(A) + r(B) - n \le r(AB)$（Sylvester不等式，$A$ 为 $m \times n$，$B$ 为 $n \times s$）
> 7. 若 $AB = O$（$A$ 为 $m \times n$，$B$ 为 $n \times s$），则 $r(A) + r(B) \le n$
> 8. $r(A^TA) = r(A)$，$r(AA^T) = r(A)$
> 9. $r\begin{pmatrix} A & O \\ O & B \end{pmatrix} = r(A) + r(B)$

### 性质4的证明

**证明：** 设 $C = AB$。

$C$ 的列向量组可由 $A$ 的列向量组线性表示（$C$ 的第 $j$ 列 = $A$ 的列的线性组合，系数来自 $B$ 的第 $j$ 列）。

故 $r(C)$ ≤ $A$ 的列秩 = $r(A)$。

同理，$C$ 的行向量组可由 $B$ 的行向量组线性表示，故 $r(C) \le r(B)$。

综上 $r(AB) \le \min(r(A), r(B))$。 $\blacksquare$

### 性质6的证明（Sylvester不等式）

**证明：** 设 $A$ 为 $m \times n$，$B$ 为 $n \times s$。

构造分块矩阵 $\begin{pmatrix} I_n & B \\ A & O \end{pmatrix}$。

对它做初等变换：
$$
\begin{pmatrix} I_n & B \\ A & O \end{pmatrix} \xrightarrow{R_2 - AR_1} \begin{pmatrix} I_n & B \\ O & -AB \end{pmatrix}
$$

$$
\begin{pmatrix} I_n & B \\ A & O \end{pmatrix} \xrightarrow{C_2 - BC_1} \begin{pmatrix} I_n & O \\ A & -AB \end{pmatrix}
$$

第一种变换：$r = n + r(AB)$
第二种变换：$r = r(A) + n$（若 $AB = O$ 则后一种有误，需要用更精细的论证）

更直接的证明：考虑 $AB$ 的列空间。$AB$ 的列空间 ⊆ $A$ 的列空间。

$AB$ 的列空间维数 = $r(AB)$。$A$ 的列空间维数 = $r(A)$。

$B$ 的零空间维数 = $n - r(B)$。$A$ 在 $B$ 的零空间上的限制，核的维数 ≤ $n - r(B)$。

由维数公式：$r(AB) \ge r(B) - (n - r(A)) = r(A) + r(B) - n$。 $\blacksquare$

---

## 四、秩与行列式的关系

> [!theorem|blue] 秩与行列式的关系
> 设 $A$ 为 $n$ 阶方阵，则：
> 1. $r(A) = n$ $\Leftrightarrow$ $|A| \neq 0$ $\Leftrightarrow$ $A$ 可逆
> 2. $r(A) < n$ $\Leftrightarrow$ $|A| = 0$ $\Leftrightarrow$ $A$ 不可逆
> 3. $r(A) = n-1$ $\Leftrightarrow$ $|A| = 0$ 且存在 $(n-1)$ 阶非零子式

**推论：**
- $n$ 阶方阵 $A$ 的秩为 $n$ 当且仅当 $A$ 的行列式不为零
- $r(A) = r$ 当且仅当 $A$ 中有 $r$ 阶非零子式且所有 $(r+1)$ 阶子式都为零

---

## 五、秩的高级性质与应用

### 5.1 分块矩阵的秩

> [!theorem|blue] 分块矩阵的秩
> $$r\begin{pmatrix} A & C \\ O & B \end{pmatrix} \ge r(A) + r(B)$$
> $$r\begin{pmatrix} A & O \\ O & B \end{pmatrix} = r(A) + r(B)$$

### 5.2 秩与线性方程组

> [!theorem|blue] 秩与方程组解的关系
> - $Ax = 0$ 有非零解 $\Leftrightarrow$ $r(A) < n$
> - $Ax = b$ 有解 $\Leftrightarrow$ $r(A) = r(A|b)$
> - $Ax = b$ 有唯一解 $\Leftrightarrow$ $r(A) = r(A|b) = n$
> - $Ax = b$ 有无穷多解 $\Leftrightarrow$ $r(A) = r(A|b) < n$

### 5.3 重要等式与不等式

**例3：** 设 $A$ 为 $n$ 阶方阵，证明 $r(A^n) = r(A^{n+1}) = r(A^{n+2}) = \cdots$

**证明：** 先证明若 $r(A^k) = r(A^{k+1})$，则 $r(A^{k+1}) = r(A^{k+2})$。

若 $r(A^k) = r(A^{k+1})$，即 $r(A^k) = r(A \cdot A^k)$。

$A^{k+1}x = 0$ 与 $A^kx = 0$ 同解（因为 $r(A^{k+1}) = r(A^k)$ 意味着 $A^k$ 的列空间与 $A^{k+1}$ 的列空间维数相同，且 $A^{k+1}$ 的列空间 ⊆ $A^k$ 的列空间，故两者相等）。

所以 $A^{k+2}x = 0$ 与 $A^{k+1}x = 0$ 同解，即 $r(A^{k+1}) = r(A^{k+2})$。

由于 $r(A) \ge r(A^2) \ge r(A^3) \ge \cdots \ge 0$ 是单调递减的非负整数序列，必在某处稳定。

故存在 $k \le n$ 使得 $r(A^k) = r(A^{k+1}) = \cdots$。 $\blacksquare$

---

## 六、求秩的综合例题

**例4：** 设 $A = \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & b \\ 2 & 3 & a & 4 \\ 3 & 5 & 1 & 7 \end{pmatrix}$，讨论 $r(A)$ 与参数 $a, b$ 的关系。

**解：**

$$
A \xrightarrow{r_3-2r_1, r_4-3r_1} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & b \\ 0 & 1 & a-2 & 2 \\ 0 & 2 & -2 & 4 \end{pmatrix}
$$

$r_3 - r_2, r_4 - 2r_2$：
$$
\rightarrow \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & -1 & b \\ 0 & 0 & a-1 & 2-b \\ 0 & 0 & 0 & 4-2b \end{pmatrix}
$$

**情况分析：**

1. 若 $a \neq 1$ 且 $b \neq 2$：$r(A) = 4$
2. 若 $a = 1$ 且 $b = 2$：$r(A) = 2$
3. 若 $a = 1$ 且 $b \neq 2$：$r(A) = 3$
4. 若 $a \neq 1$ 且 $b = 2$：$r(A) = 3$

---

## 七、易错点总结

> [!warning|red] 常见错误清单
> 1. **秩是非零子式的最高阶数**：不是"非零元素的个数"
> 2. **$r(AB) \le \min(r(A), r(B))$**：等号不一定成立
> 3. **$r(A+B) \le r(A) + r(B)$**：不是 $r(A) + r(B)$
> 4. **$r(A) = r(A^T)$**：行秩 = 列秩
> 5. **初等变换不改变秩**：但可能改变行列式
> 6. **$r(A) = 0$ 当且仅当 $A = O$**：注意零矩阵的秩为0
> 7. **满秩方阵等价于可逆**：$r(A) = n \Leftrightarrow |A| \neq 0$
> 8. **$AB = O$ 的秩关系**：$r(A) + r(B) \le n$（不是 $\le m$）

---

## 八、本讲小结

| 性质 | 公式 |
|------|------|
| 基本范围 | $0 \le r(A) \le \min(m,n)$ |
| 转置不变 | $r(A) = r(A^T)$ |
| 乘积秩 | $r(AB) \le \min(r(A), r(B))$ |
| 和的秩 | $r(A+B) \le r(A) + r(B)$ |
| Sylvester | $r(A) + r(B) - n \le r(AB)$ |
| $AB=O$ | $r(A) + r(B) \le n$ |
| 满秩等价 | $r(A) = n \Leftrightarrow \|A\| \neq 0$ |

> [!tip|blue] 考研重点
> 矩阵的秩是线性代数的核心概念，贯穿向量组、方程组、特征值等各个专题。$AB = O$ 时 $r(A) + r(B) \le n$ 和 Sylvester 不等式是考研证明题的两大工具。秩的计算必须熟练掌握初等变换法。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 8：等价矩阵]] — 等价矩阵
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 11：极大线性无关组与向量组的秩]] — 向量组的秩
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/04-线性方程组/Lecture 14：齐次线性方程组]] — 方程组
