---
title: Lecture 05 - 特征值与特征向量
subject: 线性代数
chapter: 第五章
lecture: 05
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 05: 特征值与特征向量

## 一、特征值与特征向量的定义

### 1.1 定义

<span style="background-color: #ccc1d9">**定义（特征值与特征向量）**</span> 设 $\mathbf{A}$ 为 $n$ 阶矩阵，若存在数 $\lambda$ 和 $n$ 维非零向量 $\boldsymbol{\xi}$ 使得

$$\mathbf{A}\boldsymbol{\xi} = \lambda\boldsymbol{\xi}$$

则称 $\lambda$ 为 $\mathbf{A}$ 的**特征值**，$\boldsymbol{\xi}$ 为 $\mathbf{A}$ 的属于特征值 $\lambda$ 的**特征向量**。

### 1.2 特征多项式与特征方程

<span style="background-color: #ccc1d9">**定义（特征多项式）**</span> $|\lambda\mathbf{E} - \mathbf{A}|$ 称为矩阵 $\mathbf{A}$ 的**特征多项式**。

<span style="background-color: #ccc1d9">**定义（特征方程）**</span> $|\lambda\mathbf{E} - \mathbf{A}| = 0$ 称为矩阵 $\mathbf{A}$ 的**特征方程**。

特征方程的根即为矩阵的特征值。

---

## 二、特征方程与特征多项式

### 2.1 特征多项式的展开

设 $\mathbf{A} = (a_{ij})$，则

$$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda - a_{11} & -a_{12} & \cdots & -a_{1n} \\ -a_{21} & \lambda - a_{22} & \cdots & -a_{2n} \\ \vdots & \vdots & & \vdots \\ -a_{n1} & -a_{n2} & \cdots & \lambda - a_{nn} \end{vmatrix}$$

展开后是关于 $\lambda$ 的 $n$ 次多项式。

### 2.2 特征值的性质

<span style="background-color: #8db3e2">**定理（根与系数关系）**</span> 设 $\lambda_1, \lambda_2, \cdots, \lambda_n$ 是 $\mathbf{A}$ 的 $n$ 个特征值（重根按重数计），则：
- $\lambda_1 + \lambda_2 + \cdots + \lambda_n = \text{tr}(\mathbf{A}) = a_{11} + a_{22} + \cdots + a_{nn}$（迹）
- $\lambda_1 \lambda_2 \cdots \lambda_n = |\mathbf{A}|$（行列式）

---

## 三、特征值的性质

<span style="background-color: #8db3e2">**性质1**</span> 矩阵 $\mathbf{A}$ 与其转置 $\mathbf{A}^T$ 有相同的特征值。

<span style="background-color: #8db3e2">**性质2**</span> 若 $\lambda$ 是 $\mathbf{A}$ 的特征值，则：
- $\lambda^k$ 是 $\mathbf{A}^k$ 的特征值
- 当 $\mathbf{A}$ 可逆时，$\lambda^{-1}$ 是 $\mathbf{A}^{-1}$ 的特征值

<span style="background-color: #8db3e2">**性质3**</span> 若 $\lambda_1, \lambda_2, \cdots, \lambda_m$ 是 $\mathbf{A}$ 的两两不同的特征值，$\boldsymbol{\xi}_i$ 是属于 $\lambda_i$ 的特征向量，则 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_m$ 线性无关。

<span style="background-color: #8db3e2">**性质4**</span> 若 $\lambda$ 是 $\mathbf{A}$ 的 $k$ 重特征值，则属于 $\lambda$ 的线性无关特征向量的个数 $\leq k$。

---

## 四、特征向量的性质

<span style="background-color: #8db3e2">**性质1**</span> 属于不同特征值的特征向量线性无关。

<span style="background-color: #8db3e2">**性质2**</span> 若 $\lambda$ 是 $\mathbf{A}$ 的特征值，则属于 $\lambda$ 的全部特征向量加上零向量构成特征子空间 $V_\lambda$。

<span style="background-color: #8db3e2">**性质3**</span> 若 $\boldsymbol{\xi}$ 是 $\mathbf{A}$ 的特征向量，则 $c\boldsymbol{\xi}$（$c \neq 0$）仍是 $\mathbf{A}$ 的特征向量。

<span style="background-color: #8db3e2">**性质4**</span> 若 $\boldsymbol{\xi}_1, \boldsymbol{\xi}_2$ 是属于同一特征值 $\lambda$ 的特征向量，则 $k_1\boldsymbol{\xi}_1 + k_2\boldsymbol{\xi}_2$（$k_1, k_2$ 不全为零）仍是 $\lambda$ 的特征向量。

---

## 五、相似矩阵

### 5.1 相似矩阵的定义

<span style="background-color: #ccc1d9">**定义（相似矩阵）**</span> 设 $\mathbf{A}, \mathbf{B}$ 均为 $n$ 阶矩阵，若存在可逆矩阵 $\mathbf{P}$ 使得 $\mathbf{P}^{-1}\mathbf{A}\mathbf{P} = \mathbf{B}$，则称 $\mathbf{A}$ 与 $\mathbf{B}$ **相似**，记作 $\mathbf{A} \sim \mathbf{B}$。

### 5.2 相似矩阵的性质

<span style="background-color: #8db3e2">**性质**</span>
- 若 $\mathbf{A} \sim \mathbf{B}$，则 $|\mathbf{A}| = |\mathbf{B}|$
- 若 $\mathbf{A} \sim \mathbf{B}$，则 $\text{tr}(\mathbf{A}) = \text{tr}(\mathbf{B})$
- 若 $\mathbf{A} \sim \mathbf{B}$，则 $\mathbf{A}$ 与 $\mathbf{B}$ 有相同的特征值
- 若 $\mathbf{A} \sim \mathbf{B}$，则 $\mathbf{A}^k \sim \mathbf{B}^k$
- 若 $\mathbf{A}$ 可逆，则 $\mathbf{A}^{-1} \sim \mathbf{B}^{-1}$

---

## 六、矩阵的相似对角化

### 6.1 可对角化的条件

<span style="background-color: #ccc1d9">**定义（可对角化）**</span> 若存在可逆矩阵 $\mathbf{P}$ 使得 $\mathbf{P}^{-1}\mathbf{A}\mathbf{P} = \boldsymbol{\Lambda}$ 为对角矩阵，则称 $\mathbf{A}$ **可对角化**。

<span style="background-color: #8db3e2">**定理**</span> $n$ 阶矩阵 $\mathbf{A}$ 可对角化的充要条件是 $\mathbf{A}$ 有 $n$ 个线性无关的特征向量。

<span style="background-color: #8db3e2">**推论**</span> 若 $\mathbf{A}$ 有 $n$ 个两两不同的特征值，则 $\mathbf{A}$ 一定可对角化。

### 6.2 对角化的步骤

<span style="background-color: #8db3e2">**步骤**</span>
1. 求特征方程 $|\lambda\mathbf{E} - \mathbf{A}| = 0$ 的全部根
2. 对每个特征值 $\lambda_i$，求 $(\lambda_i\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$ 的基础解系
3. 将所有特征向量拼成矩阵 $\mathbf{P} = [\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \cdots, \boldsymbol{\xi}_n]$
4. $\mathbf{P}^{-1}\mathbf{A}\mathbf{P} = \text{diag}(\lambda_1, \lambda_2, \cdots, \lambda_n)$

---

## 七、实对称矩阵的对角化

### 7.1 实对称矩阵的特殊性质

<span style="background-color: #8db3e2">**定理1**</span> 实对称矩阵的特征值都是实数。

<span style="background-color: #8db3e2">**定理2**</span> 实对称矩阵属于不同特征值的特征向量两两正交。

<span style="background-color: #8db3e2">**定理3**</span> 设 $\mathbf{A}$ 为 $n$ 阶实对称矩阵，则存在正交矩阵 $\mathbf{Q}$ 使得

$$\mathbf{Q}^{-1}\mathbf{A}\mathbf{Q} = \mathbf{Q}^T\mathbf{A}\mathbf{Q} = \text{diag}(\lambda_1, \lambda_2, \cdots, \lambda_n)$$

其中 $\lambda_1, \lambda_2, \cdots, \lambda_n$ 是 $\mathbf{A}$ 的全部特征值。

### 7.2 实对称矩阵对角化的步骤

<span style="background-color: #8db3e2">**步骤**</span>
1. 求特征方程的全部特征值
2. 对每个特征值，求特征向量
3. 对重根特征值的特征向量进行施密特正交化
4. 单位化所有正交特征向量得到正交矩阵 $\mathbf{Q}$
5. $\mathbf{Q}^T\mathbf{A}\mathbf{Q} = \text{diag}(\lambda_1, \lambda_2, \cdots, \lambda_n)$

---

## 八、典型例题

### 例题1：特征值与特征向量的计算

**题目**（660题-369变式）设 $\boldsymbol{\alpha}=(1,3,-2)^{\mathrm{T}},\boldsymbol{\beta}=(2,0,0)^{\mathrm{T}},\mathbf{A}=\boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}}$，求 $\mathbf{A}$ 的特征值和特征向量。

**思路**：利用 $\mathbf{A} = \boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}}$ 的特殊结构。

**解答**：
$\mathbf{A} = \begin{bmatrix} 2 & 0 & 0 \\ 6 & 0 & 0 \\ -4 & 0 & 0 \end{bmatrix}$，秩为1。

由 $|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda-2 & 0 & 0 \\ -6 & \lambda & 0 \\ 4 & 0 & \lambda \end{vmatrix} = \lambda^2(\lambda-2) = 0$

得特征值 $\lambda_1 = 2, \lambda_2 = \lambda_3 = 0$。

对 $\lambda_1 = 2$：解 $(2\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} 0 & 0 & 0 \\ -6 & 2 & 0 \\ 4 & 0 & 2 \end{bmatrix} \rightarrow \begin{bmatrix} -6 & 2 & 0 \\ 4 & 0 & 2 \\ 0 & 0 & 0 \end{bmatrix}$，特征向量 $\boldsymbol{\xi}_1 = (1,3,-2)^T$

对 $\lambda_2 = \lambda_3 = 0$：解 $(0\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} -2 & 0 & 0 \\ -6 & 0 & 0 \\ -4 & 0 & 0 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}$，特征向量 $\boldsymbol{\xi}_2 = (0,1,0)^T, \boldsymbol{\xi}_3 = (0,0,1)^T$

**总结**：秩为1的矩阵只有一个非零特征值。

---

### 例题2：相似矩阵的判定

**题目**（660题-393变式）设 $\mathbf{A} = \begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix}$，判断 $\mathbf{A}$ 是否可对角化，如可对角化，求出对角化矩阵。

**思路**：求特征值和特征向量。

**解答**：
$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda-1 & -2 \\ -2 & \lambda-1 \end{vmatrix} = (\lambda-1)^2 - 4 = \lambda^2 - 2\lambda - 3 = (\lambda-3)(\lambda+1)$

特征值 $\lambda_1 = 3, \lambda_2 = -1$。

对 $\lambda_1 = 3$：解 $(3\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} 2 & -2 \\ -2 & 2 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & -1 \\ 0 & 0 \end{bmatrix}$，$\boldsymbol{\xi}_1 = (1,1)^T$

对 $\lambda_2 = -1$：解 $(-\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} -2 & -2 \\ -2 & -2 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 1 \\ 0 & 0 \end{bmatrix}$，$\boldsymbol{\xi}_2 = (1,-1)^T$

两个特征值不同，$\boldsymbol{\xi}_1, \boldsymbol{\xi}_2$ 线性无关，$\mathbf{A}$ 可对角化。

$\mathbf{P} = \begin{bmatrix} 1 & 1 \\ 1 & -1 \end{bmatrix}$，$\mathbf{P}^{-1}\mathbf{A}\mathbf{P} = \begin{bmatrix} 3 & 0 \\ 0 & -1 \end{bmatrix}$

**总结**：有 $n$ 个不同特征值则必可对角化。

---

### 例题3：实对称矩阵的正交对角化

**题目**（660题-397变式）设 $\mathbf{A} = \begin{bmatrix} 2 & 2 & 2 \\ 2 & 2 & 2 \\ 2 & 2 & 2 \end{bmatrix}$，求正交矩阵 $\mathbf{Q}$ 使 $\mathbf{Q}^T\mathbf{A}\mathbf{Q}$ 为对角矩阵。

**思路**：实对称矩阵必可正交对角化。

**解答**：
$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda-2 & -2 & -2 \\ -2 & \lambda-2 & -2 \\ -2 & -2 & \lambda-2 \end{vmatrix} = (\lambda-6)(\lambda)^2$

特征值 $\lambda_1 = 6, \lambda_2 = \lambda_3 = 0$。

对 $\lambda_1 = 6$：解 $(6\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} 4 & -2 & -2 \\ -2 & 4 & -2 \\ -2 & -2 & 4 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & -1 & 0 \\ 0 & 1 & -1 \\ 0 & 0 & 0 \end{bmatrix}$，$\boldsymbol{\xi}_1 = (1,1,1)^T$

对 $\lambda_2 = \lambda_3 = 0$：解 $(0\mathbf{E} - \mathbf{A})\mathbf{x} = \mathbf{0}$

$\begin{bmatrix} -2 & -2 & -2 \\ -2 & -2 & -2 \\ -2 & -2 & -2 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 1 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}$，取正交基：

$\boldsymbol{\xi}_2 = (1,-1,0)^T$（取 $x_1 = 1, x_2 = -1, x_3 = 0$）

$\boldsymbol{\xi}_3 = (1,1,-2)^T$（与 $\boldsymbol{\xi}_2$ 正交，取 $x_1 = 1, x_2 = 1, x_3 = -2$）

正交化：$\boldsymbol{\eta}_1 = \boldsymbol{\xi}_1$ 已正交

$\boldsymbol{\eta}_2 = \boldsymbol{\xi}_2$

$\boldsymbol{\eta}_3 = \boldsymbol{\xi}_3 - \frac{(\boldsymbol{\xi}_3, \boldsymbol{\eta}_2)}{(\boldsymbol{\eta}_2, \boldsymbol{\eta}_2)}\boldsymbol{\eta}_2 = (1,1,-2)^T - \frac{0}{2}\boldsymbol{\eta}_2 = (1,1,-2)^T$

单位化：

$\mathbf{q}_1 = \frac{1}{\sqrt{3}}(1,1,1)^T$
$\mathbf{q}_2 = \frac{1}{\sqrt{2}}(1,-1,0)^T$
$\mathbf{q}_3 = \frac{1}{\sqrt{6}}(1,1,-2)^T$

$\mathbf{Q} = \begin{bmatrix} \frac{1}{\sqrt{3}} & \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{6}} \\ \frac{1}{\sqrt{3}} & -\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{6}} \\ \frac{1}{\sqrt{3}} & 0 & -\frac{2}{\sqrt{6}} \end{bmatrix}$

$\mathbf{Q}^T\mathbf{A}\mathbf{Q} = \begin{bmatrix} 6 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}$

**总结**：实对称矩阵对角化时，重根特征向量需要施密特正交化。

---

### 例题4：矩阵幂的计算

**题目**（660题-376变式）设 $\mathbf{A} = \begin{bmatrix} 2 & -1 & 3 \\ 4 & -2 & 6 \\ -2 & 1 & -3 \end{bmatrix}$，求 $\mathbf{A}^{10}$。

**思路**：先判断 $\mathbf{A}$ 是否可对角化，利用对角化求幂。

**解答**：
观察到 $\mathbf{A}$ 的列向量线性相关，$r(\mathbf{A}) = 1$。

设 $\mathbf{A} = \begin{bmatrix} 2 \\ 4 \\ -2 \end{bmatrix}[1, -\frac{1}{2}, \frac{3}{2}]$？不完全是。

先求特征值：$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda-2 & 1 & -3 \\ -4 & \lambda+2 & -6 \\ 2 & -1 & \lambda+3 \end{vmatrix}$

经计算：$(\lambda+1)(\lambda^2-5\lambda) = 0$，得 $\lambda_1 = -1, \lambda_2 = 0, \lambda_3 = 5$？

但 $r(\mathbf{A}) = 1$，所以至多有一个非零特征值。

重新计算：$|\lambda\mathbf{E} - \mathbf{A}| = \lambda^2(\lambda - ?)$

实际上，设 $\mathbf{A} = \boldsymbol{\alpha}\boldsymbol{\beta}^T$ 形式？$\mathbf{A}$ 的秩为1，所以特征值为 $\lambda_1 = \text{tr}(\mathbf{A}), \lambda_2 = \lambda_3 = 0$。

$\text{tr}(\mathbf{A}) = 2 + (-2) + (-3) = -3$

所以特征值 $\lambda_1 = -3, \lambda_2 = \lambda_3 = 0$。

$\mathbf{A}$ 可对角化（因为有3个线性无关特征向量？秩为1，零特征值重数为2，存在两个线性无关特征向量）。

设 $\mathbf{P} = [\boldsymbol{\xi}_1, \boldsymbol{\xi}_2, \boldsymbol{\xi}_3]$，其中 $\boldsymbol{\xi}_1$ 是 $\lambda_1 = -3$ 的特征向量，$\boldsymbol{\xi}_2, \boldsymbol{\xi}_3$ 是 $\lambda_2 = \lambda_3 = 0$ 的特征向量。

$\mathbf{A} = \mathbf{P}\text{diag}(-3,0,0)\mathbf{P}^{-1}$

$\mathbf{A}^{10} = \mathbf{P}\text{diag}((-3)^{10},0,0)\mathbf{P}^{-1} = \mathbf{P}\text{diag}(3^{10},0,0)\mathbf{P}^{-1}$

由于 $\mathbf{A}$ 秩为1，$\mathbf{A}^{10} = (3^{10}) \boldsymbol{\xi}_1 \boldsymbol{\eta}_1^T \mathbf{P}^{-1}$？这很复杂。

更简单的方法：直接计算 $\mathbf{A}^2$：

$\mathbf{A} = \begin{bmatrix} 2 & -1 & 3 \\ 4 & -2 & 6 \\ -2 & 1 & -3 \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \\ -2 \end{bmatrix}[1, -\frac{1}{2}, \frac{3}{2}]$？不对。

实际上 $\mathbf{A} = \begin{bmatrix} 1 \\ 2 \\ -1 \end{bmatrix}[2, -1, 3]$

验证：$\begin{bmatrix} 1 \\ 2 \\ -1 \end{bmatrix}[2, -1, 3] = \begin{bmatrix} 2 & -1 & 3 \\ 4 & -2 & 6 \\ -2 & 1 & -3 \end{bmatrix} = \mathbf{A}$ ✓

所以 $\mathbf{A}^2 = (\boldsymbol{\alpha}\boldsymbol{\beta}^T)(\boldsymbol{\alpha}\boldsymbol{\beta}^T) = \boldsymbol{\alpha}(\boldsymbol{\beta}^T\boldsymbol{\alpha})\boldsymbol{\beta}^T$

$\boldsymbol{\beta}^T\boldsymbol{\alpha} = [2,-1,3]\begin{bmatrix} 1 \\ 2 \\ -1 \end{bmatrix} = 2 - 2 - 3 = -3$

$\mathbf{A}^2 = -3\boldsymbol{\alpha}\boldsymbol{\beta}^T = -3\mathbf{A}$

$\mathbf{A}^3 = \mathbf{A}^2 \cdot \mathbf{A} = (-3\mathbf{A})\mathbf{A} = -3\mathbf{A}^2 = 9\mathbf{A}$

归纳：$\mathbf{A}^n = (-3)^{n-1}\mathbf{A}$（$n \geq 1$）

所以 $\mathbf{A}^{10} = (-3)^9 \mathbf{A} = -3^9 \mathbf{A}$

**总结**：秩为1的矩阵可表示为列向量乘行向量，利用结合律简化幂运算。

---

## 九、解题方法总结

### 9.1 特征值计算方法

| 方法 | 适用情况 |
|------|----------|
| 定义法 | 直接解 $\mathbf{A}\boldsymbol{\xi} = \lambda\boldsymbol{\xi}$ |
| 特征多项式 | 解 $|\lambda\mathbf{E} - \mathbf{A}| = 0$ |
| 迹与行列式 | $\sum \lambda_i = \text{tr}(\mathbf{A}), \prod \lambda_i = |\mathbf{A}|$ |

### 9.2 对角化判定方法

| 条件 | 结论 |
|------|------|
| 有 $n$ 个不同特征值 | 必可对角化 |
| 重的特征值子空间维数 = 重数 | 可对角化 |
| 存在重特征值且子空间维数 < 重数 | 不可对角化 |

### 9.3 常见易错点

1. **忽略重根情况**：有重特征值时不一定有足够的线性无关特征向量
2. **特征向量方向**：特征向量乘以常数还是特征向量，但方向（符号）不同
3. **正交对角化**：实对称矩阵要用正交矩阵，不是任意可逆矩阵
4. **相似与合同混淆**：相似要求 $\mathbf{P}^{-1}\mathbf{A}\mathbf{P}$，合同要求 $\mathbf{P}^{T}\mathbf{A}\mathbf{P}$

---

## 十、练习题精选

### 基础练习

1. 求矩阵 $\mathbf{A} = \begin{bmatrix} 3 & 1 \\ 2 & 2 \end{bmatrix}$ 的特征值和特征向量。

2. 判断 $\mathbf{A} = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}$ 是否可对角化。

3. 设 $\mathbf{A}$ 为三阶矩阵，特征值为 $1, 2, -1$，求 $|\mathbf{A} + \mathbf{E}|$。

### 提高练习

4. 设 $\mathbf{A}^2 = \mathbf{E}$，证明 $\mathbf{A}$ 可对角化。

5. 设 $\mathbf{A}$ 为正交矩阵，证明 $|\mathbf{A}| = \pm 1$，且若 $|\mathbf{A}| = 1$ 则 $\mathbf{A}$ 的特征值只能是 $1$ 或 $-1$（对于实特征值）。

---

## 参考答案提示

1. $|\lambda\mathbf{E} - \mathbf{A}| = (\lambda-1)(\lambda-4)$，$\lambda_1 = 1, \lambda_2 = 4$
   - $\lambda_1 = 1$ 对应 $\boldsymbol{\xi}_1 = (1,-2)^T$
   - $\lambda_2 = 4$ 对应 $\boldsymbol{\xi}_2 = (1,1)^T$

2. 不可对角化。$\lambda = 1$（二重），但 $(\mathbf{E} - \mathbf{A}) = \begin{bmatrix} 0 & -1 \\ 0 & 0 \end{bmatrix}$，秩为1，齐次方程组只有1个线性无关解

3. $|\mathbf{A} + \mathbf{E}| = \prod (\lambda_i + 1) = (1+1)(2+1)(-1+1) = 2 \times 3 \times 0 = 0$

4. 提示：由 $\mathbf{A}^2 = \mathbf{E}$ 得 $(\mathbf{A} + \mathbf{E})(\mathbf{A} - \mathbf{E}) = \mathbf{0}$，利用特征值只能是 $\pm 1$

5. 由 $\mathbf{A}^T\mathbf{A} = \mathbf{E}$ 得 $|\mathbf{A}|^2 = 1$

---

> **注**：本 Lecture 内容涵盖特征值与特征向量的核心知识点。建议结合《基础过关660题》第393-403题进行练习巩固。
