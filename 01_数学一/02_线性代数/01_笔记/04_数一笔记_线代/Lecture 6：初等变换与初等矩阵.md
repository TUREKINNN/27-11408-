---
title: Lecture 6：初等变换与初等矩阵
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 6：初等变换与初等矩阵

## 一、三种初等行（列）变换

> [!definition|purple] 三种初等行变换
> 1. **倍乘变换**：用非零常数 $k$ 乘矩阵的某一行，记为 $r_i \times k$（或 $kr_i$）
> 2. **倍加变换**：将某一行的 $k$ 倍加到另一行上，记为 $r_i + kr_j$
> 3. **换行变换**：交换两行，记为 $r_i \leftrightarrow r_j$
>
> 列变换类似，分别记为 $c_i \times k$、$c_i + kc_j$、$c_i \leftrightarrow c_j$。

**核心原则：**
- 矩阵的初等变换是**可逆的**
- 初等变换不改变矩阵的秩
- 对增广矩阵 $(A|b)$ 做初等行变换，相当于解同解方程组

---

## 二、初等矩阵

> [!definition|purple] 初等矩阵
> 由单位矩阵 $I$ 经过**一次**初等变换得到的矩阵称为**初等矩阵**。
>
> 对应三种初等变换，有三种初等矩阵：

### 2.1 倍乘初等矩阵

$$
E_i(k) = \begin{pmatrix} 1 & & & & \\ & \ddots & & & \\ & & k & & \\ & & & \ddots & \\ & & & & 1 \end{pmatrix} \quad \leftarrow \text{第 } i \text{ 行}
$$

即 $I$ 的第 $i$ 个对角元由 $1$ 改为 $k$（$k \neq 0$）。

- 行列式：$|E_i(k)| = k$
- 逆矩阵：$E_i(k)^{-1} = E_i(1/k)$

### 2.2 倍加初等矩阵

$$
E_{ij}(k) = \begin{pmatrix} 1 & & & & \\ & \ddots & & & \\ & & 1 & \cdots & k \\ & & & \ddots & \vdots \\ & & & & 1 \end{pmatrix} \quad \leftarrow \text{第 } i \text{ 行, 第 } j \text{ 列}
$$

即 $I$ 的第 $i$ 行第 $j$ 列位置由 $0$ 改为 $k$。

- 行列式：$|E_{ij}(k)| = 1$
- 逆矩阵：$E_{ij}(k)^{-1} = E_{ij}(-k)$

### 2.3 换行初等矩阵

$$
E_{ij} = \begin{pmatrix} 1 & & & & & \\ & 0 & \cdots & 1 & & \\ & \vdots & \ddots & \vdots & & \\ & 1 & \cdots & 0 & & \\ & & & & \ddots & \\ & & & & & 1 \end{pmatrix} \quad \leftarrow \text{第 } i, j \text{ 行}
$$

即 $I$ 的第 $i$ 行和第 $j$ 行交换。

- 行列式：$|E_{ij}| = -1$
- 逆矩阵：$E_{ij}^{-1} = E_{ij}$（自身就是逆）

---

## 三、初等矩阵与初等变换的关系

> [!theorem|blue] 左行右列定理
> 对矩阵 $A$ 做初等**行**变换，等价于用相应的初等矩阵**左乘** $A$；
> 对矩阵 $A$ 做初等**列**变换，等价于用相应的初等矩阵**右乘** $A$。
>
> 即：
> - $E_i(k) \cdot A$ = 对 $A$ 的第 $i$ 行乘 $k$
> - $E_{ij}(k) \cdot A$ = 把 $A$ 的第 $j$ 行的 $k$ 倍加到第 $i$ 行
> - $E_{ij} \cdot A$ = 交换 $A$ 的第 $i$ 行和第 $j$ 行
> - $A \cdot E_i(k)$ = 对 $A$ 的第 $i$ 列乘 $k$
> - $A \cdot E_{ij}(k)$ = 把 $A$ 的第 $i$ 列的 $k$ 倍加到第 $j$ 列
> - $A \cdot E_{ij}$ = 交换 $A$ 的第 $i$ 列和第 $j$ 列

**证明思路（以倍加为例）：**

设 $A = \begin{pmatrix} \alpha_1 \\ \vdots \\ \alpha_n \end{pmatrix}$（按行分块），则

$$
E_{ij}(k) \cdot A = \begin{pmatrix} \alpha_1 \\ \vdots \\ \alpha_i + k\alpha_j \\ \vdots \\ \alpha_n \end{pmatrix}
$$

恰好就是对 $A$ 做 $r_i + kr_j$ 变换的结果。

---

## 四、初等矩阵与可逆矩阵的关系

> [!theorem|blue] 可逆矩阵的分解定理
> 1. 任何可逆矩阵都可以表示为有限个初等矩阵的乘积
> 2. 任何矩阵 $A$ 都可以通过初等行变换化为行阶梯形矩阵
> 3. 可逆矩阵可以通过初等行变换化为单位矩阵

**证明思路：**

$A$ 可逆 $\Leftrightarrow |A| \neq 0$ $\Leftrightarrow A$ 可以通过初等行变换化为 $I$

设 $P_k \cdots P_2 P_1 A = I$，则 $A = P_1^{-1} P_2^{-1} \cdots P_k^{-1}$

每个 $P_i^{-1}$ 仍是初等矩阵，故 $A$ 可表为初等矩阵之积。

### 初等变换法求逆的理论基础

$(A|I) \xrightarrow{\text{初等行变换}} (I|A^{-1})$

等价于：存在初等矩阵 $P_1, P_2, \cdots, P_k$ 使得 $P_k \cdots P_1 A = I$

则 $A^{-1} = P_k \cdots P_1 = P_k \cdots P_1 I$，即对 $I$ 做同样的变换。

---

## 五、初等矩阵的应用

### 5.1 矩阵分解

**例1：** 设 $A = \begin{pmatrix} 1 & 2 \\ 3 & 7 \end{pmatrix}$，将 $A$ 表示为初等矩阵之积。

**解：** 对 $A$ 做初等行变换化为 $I$，同时记录每一步对应的初等矩阵。

$$
A = \begin{pmatrix} 1 & 2 \\ 3 & 7 \end{pmatrix} \xrightarrow{r_2 - 3r_1} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \xrightarrow{r_1 - 2r_2} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
$$

对应初等矩阵：
$$
P_2 = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix}, \quad P_1 = \begin{pmatrix} 1 & 0 \\ -3 & 1 \end{pmatrix}
$$

$P_2 P_1 A = I$，故 $A = P_1^{-1} P_2^{-1} = \begin{pmatrix} 1 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$

### 5.2 分块矩阵的逆

**例2：** 求 $\begin{pmatrix} A & C \\ O & B \end{pmatrix}^{-1}$（其中 $A, B$ 可逆）。

**解：** 设逆矩阵为 $\begin{pmatrix} X & Y \\ Z & W \end{pmatrix}$，则

$$
\begin{pmatrix} A & C \\ O & B \end{pmatrix} \begin{pmatrix} X & Y \\ Z & W \end{pmatrix} = \begin{pmatrix} I & O \\ O & I \end{pmatrix}
$$

展开得：
- $AX + CZ = I$
- $AY + CW = O$
- $BZ = O$ → $Z = O$
- $BW = I$ → $W = B^{-1}$

代入：$AX = I$ → $X = A^{-1}$，$AY + CB^{-1} = O$ → $Y = -A^{-1}CB^{-1}$

$$
\boxed{\begin{pmatrix} A & C \\ O & B \end{pmatrix}^{-1} = \begin{pmatrix} A^{-1} & -A^{-1}CB^{-1} \\ O & B^{-1} \end{pmatrix}}
$$

### 5.3 等价标准形

> [!theorem|blue] 矩阵的等价标准形
> 任何 $m \times n$ 矩阵 $A$（秩为 $r$）都可以通过初等变换化为标准形：
> $$
> \begin{pmatrix} I_r & O \\ O & O \end{pmatrix}
> $$
> 即存在可逆矩阵 $P$（$m$ 阶）和 $Q$（$n$ 阶）使得
> $$
> PAQ = \begin{pmatrix} I_r & O \\ O & O \end{pmatrix}
> $$

---

## 六、易错点总结

> [!warning|red] 常见错误清单
> 1. **"左行右列"**：初等矩阵左乘影响行，右乘影响列
> 2. **初等矩阵的逆**：$E_i(k)^{-1} = E_i(1/k)$，$E_{ij}(k)^{-1} = E_{ij}(-k)$，$E_{ij}^{-1} = E_{ij}$
> 3. **初等矩阵的行列式**：倍乘为 $k$，倍加为 $1$，换行为 $-1$
> 4. **求逆时只能用行变换**：不能混用列变换
> 5. **初等矩阵是"一次"变换**：做了两次变换就不是初等矩阵
> 6. **等价标准形的秩**：标准形中的 $I_r$ 的阶数 $r$ 等于原矩阵的秩
> 7. **分块矩阵求逆**：不要忘记非对角块 $-A^{-1}CB^{-1}$
> 8. **初等矩阵可逆**：任何初等矩阵都可逆，其逆仍是初等矩阵

---

## 七、本讲小结

| 初等变换 | 初等矩阵 | 行列式 | 逆矩阵 |
|---------|---------|--------|--------|
| $r_i \times k$ | $E_i(k)$ | $k$ | $E_i(1/k)$ |
| $r_i + kr_j$ | $E_{ij}(k)$ | $1$ | $E_{ij}(-k)$ |
| $r_i \leftrightarrow r_j$ | $E_{ij}$ | $-1$ | $E_{ij}$ |

> [!tip|blue] 考研重点
> 初等矩阵是连接矩阵运算和初等变换的桥梁。"左行右列"定理是理解矩阵分解和等价标准形的基础。分块矩阵的逆公式在考研大题中经常出现。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 4：矩阵的逆]] — 逆矩阵
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 7：矩阵方程]] — 矩阵方程
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 8：等价矩阵]] — 等价矩阵
