---
title: Lecture 03 - 向量
subject: 线性代数
chapter: 第三章
lecture: 03
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 03: 向量

## 一、n维向量的概念

### 1.1 向量的定义

<span style="background-color: #ccc1d9">**定义（n维向量）**</span> 由 $n$ 个数组成的有序数组称为 $n$ 维向量，记作

$$\boldsymbol{\alpha} = (a_1, a_2, \cdots, a_n)^T \text{ 或 } \begin{bmatrix} a_1 \\ a_2 \\ \vdots \\ a_n \end{bmatrix}$$

其中 $a_i$ 称为向量的第 $i$ 个分量。

### 1.2 向量的运算

**加法**：$\boldsymbol{\alpha} + \boldsymbol{\beta} = (a_1 + b_1, a_2 + b_2, \cdots, a_n + b_n)^T$

**数乘**：$k\boldsymbol{\alpha} = (ka_1, ka_2, \cdots, ka_n)^T$

---

## 二、向量的线性组合与线性表示

### 2.1 线性组合

<span style="background-color: #ccc1d9">**定义（线性组合）**</span> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 为 $n$ 维向量，$k_1, k_2, \cdots, k_s$ 为常数，则

$$\boldsymbol{\beta} = k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s$$

称为向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的一个**线性组合**。

### 2.2 线性表示

<span style="background-color: #ccc1d9">**定义（线性表示）**</span> 若存在常数 $k_1, k_2, \cdots, k_s$ 使得

$$\boldsymbol{\beta} = k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s$$

则称 $\boldsymbol{\beta}$ 可由向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ **线性表示**。

<span style="background-color: #8db3e2">**定理**</span> $\boldsymbol{\beta}$ 可由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性表示的充要条件是矩阵 $(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$ 的秩等于增广矩阵 $(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s, \boldsymbol{\beta})$ 的秩。

---

## 三、向量组的线性相关与线性无关

### 3.1 线性相关

<span style="background-color: #ccc1d9">**定义（线性相关）**</span> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 为 $n$ 维向量，若存在一组不全为零的常数 $k_1, k_2, \cdots, k_s$ 使得

$$k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + \cdots + k_s\boldsymbol{\alpha}_s = \mathbf{0}$$

则称向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ **线性相关**。

### 3.2 线性无关

<span style="background-color: #ccc1d9">**定义（线性无关）**</span> 若向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 只有当 $k_1 = k_2 = \cdots = k_s = 0$ 时才能使上式成立，则称该向量组**线性无关**。

### 3.3 重要结论

<span style="background-color: #8db3e2">**定理**</span> 向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性相关的充要条件是至少有一个向量可以由其余向量线性表示。

<span style="background-color: #8db3e2">**推论**</span> 若向量组线性无关，则其中任何一个向量都不能由其余向量线性表示。

---

## 四、线性相关性的判定定理

<span style="background-color: #8db3e2">**定理1**</span> $n$ 个 $n$ 维向量 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 线性无关的充要条件是行列式 $|\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n| \neq 0$。

<span style="background-color: #8db3e2">**定理2**</span> 若向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性无关，则它的任一扩充组（添加向量）是否线性相关取决于所添向量是否能由原向量组线性表示。

<span style="background-color: #8db3e2">**定理3**</span> 若向量组中有一个部分组线性相关，则整个向量组线性相关。（部分相关则整体相关）

<span style="background-color: #8db3e2">**定理4**</span> 若向量组线性无关，则它的任一部分组都线性无关。（整体无关则部分无关）

<span style="background-color: #8db3e2">**定理5**</span> $n+1$ 个 $n$ 维向量必定线性相关。（维数小于向量的个数时，必线性相关）

<span style="background-color: #8db3e2">**定理6**</span> 若向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性无关，而向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s, \boldsymbol{\beta}$ 线性相关，则 $\boldsymbol{\beta}$ 必可由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 线性表示，且表示法唯一。

---

## 五、向量组的极大线性无关组

### 5.1 极大线性无关组的定义

<span style="background-color: #ccc1d9">**定义（极大线性无关组）**</span> 设向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的一个部分组 $\boldsymbol{\alpha}_{i_1}, \boldsymbol{\alpha}_{i_2}, \cdots, \boldsymbol{\alpha}_{i_r}$ 满足：
1. $\boldsymbol{\alpha}_{i_1}, \boldsymbol{\alpha}_{i_2}, \cdots, \boldsymbol{\alpha}_{i_r}$ 线性无关
2. 从原向量组中任意添加一个向量（如果还有的话），所得向量组都线性相关

则称 $\boldsymbol{\alpha}_{i_1}, \boldsymbol{\alpha}_{i_2}, \cdots, \boldsymbol{\alpha}_{i_r}$ 为该向量组的一个**极大线性无关组**。

### 5.2 极大无关组的性质

<span style="background-color: #8db3e2">**性质**</span>
- 极大线性无关组不唯一，但所含向量个数相同
- 极大无关组的向量数称为向量组的秩

---

## 六、向量组的秩

<span style="background-color: #ccc1d9">**定义（向量组的秩）**</span> 向量组 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s$ 的极大线性无关组所含向量的个数称为该向量组的秩，记作 $r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s)$。

<span style="background-color: #8db3e2">**性质**</span>
- $0 \leq r(\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_s) \leq \min\{s, n\}$
- 向量组线性无关 $\Leftrightarrow$ $r = s$
- 向量组线性相关 $\Leftrightarrow$ $r < s$

---

## 七、向量空间（基、坐标、过渡矩阵）

### 7.1 向量空间的定义

<span style="background-color: #ccc1d9">**定义（向量空间）**</span> 设 $\mathbf{V}$ 为 $n$ 维向量的非空集合，若对任意 $\boldsymbol{\alpha}, \boldsymbol{\beta} \in \mathbf{V}$ 和任意常数 $k$，有 $\boldsymbol{\alpha} + \boldsymbol{\beta} \in \mathbf{V}$，$k\boldsymbol{\alpha} \in \mathbf{V}$，则称 $\mathbf{V}$ 为**向量空间**。

### 7.2 基与坐标

<span style="background-color: #ccc1d9">**定义（基）**</span> 设 $\mathbf{V}$ 为向量空间，若 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r \in \mathbf{V}$ 满足：
1. $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 线性无关
2. $\mathbf{V}$ 中任一向量均可由 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 线性表示

则称 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 为向量空间 $\mathbf{V}$ 的一组**基**，$r$ 称为 $\mathbf{V}$ 的**维数**。

<span style="background-color: #ccc1d9">**定义（坐标）**</span> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 为向量空间 $\mathbf{V}$ 的一组基，若 $\mathbf{V}$ 中向量 $\boldsymbol{\beta}$ 可唯一地表示为

$$\boldsymbol{\beta} = x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + \cdots + x_r\boldsymbol{\alpha}_r$$

则称 $(x_1, x_2, \cdots, x_r)^T$ 为 $\boldsymbol{\beta}$ 在基 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 下的**坐标**。

### 7.3 过渡矩阵

<span style="background-color: #ccc1d9">**定义（过渡矩阵）**</span> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 和 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_n$ 是 $n$ 维向量空间 $\mathbf{V}$ 的两组基，若

$$\begin{bmatrix} \boldsymbol{\beta}_1 \\ \boldsymbol{\beta}_2 \\ \vdots \\ \boldsymbol{\beta}_n \end{bmatrix} = \mathbf{C} \begin{bmatrix} \boldsymbol{\alpha}_1 \\ \boldsymbol{\alpha}_2 \\ \vdots \\ \boldsymbol{\alpha}_n \end{bmatrix}$$

则称 $\mathbf{C}$ 为从基 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 到基 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_n$ 的**过渡矩阵**。

<span style="background-color: #8db3e2">**性质**</span> 过渡矩阵 $\mathbf{C}$ 是可逆矩阵。

---

## 八、向量的内积与正交规范化

### 8.1 内积的定义

<span style="background-color: #ccc1d9">**定义（内积）**</span> 设 $\boldsymbol{\alpha} = (a_1, a_2, \cdots, a_n)^T$，$\boldsymbol{\beta} = (b_1, b_2, \cdots, b_n)^T$，则

$$(\boldsymbol{\alpha}, \boldsymbol{\beta}) = \boldsymbol{\alpha}^T\boldsymbol{\beta} = a_1b_1 + a_2b_2 + \cdots + a_nb_n$$

称为向量 $\boldsymbol{\alpha}$ 与 $\boldsymbol{\beta}$ 的**内积**。

### 8.2 内积的性质

<span style="background-color: #8db3e2">**性质**</span>
- $(\boldsymbol{\alpha}, \boldsymbol{\beta}) = (\boldsymbol{\beta}, \boldsymbol{\alpha})$（对称性）
- $(\boldsymbol{\alpha} + \boldsymbol{\beta}, \boldsymbol{\gamma}) = (\boldsymbol{\alpha}, \boldsymbol{\gamma}) + (\boldsymbol{\beta}, \boldsymbol{\gamma})$
- $(k\boldsymbol{\alpha}, \boldsymbol{\beta}) = k(\boldsymbol{\alpha}, \boldsymbol{\beta})$
- $(\boldsymbol{\alpha}, \boldsymbol{\alpha}) \geq 0$，且 $(\boldsymbol{\alpha}, \boldsymbol{\alpha}) = 0 \Leftrightarrow \boldsymbol{\alpha} = \mathbf{0}$

### 8.3 向量的模与夹角

<span style="background-color: #ccc1d9">**定义（向量的模）**</span> $\|\boldsymbol{\alpha}\| = \sqrt{(\boldsymbol{\alpha}, \boldsymbol{\alpha})} = \sqrt{a_1^2 + a_2^2 + \cdots + a_n^2}$

<span style="background-color: #ccc1d9">**定义（单位向量）**</span> 若 $\|\boldsymbol{\alpha}\| = 1$，则称 $\boldsymbol{\alpha}$ 为**单位向量**。

<span style="background-color: #ccc1d9">**定义（正交）**</span> 若 $(\boldsymbol{\alpha}, \boldsymbol{\beta}) = 0$，则称 $\boldsymbol{\alpha}$ 与 $\boldsymbol{\beta}$ **正交**。

### 8.4 正交规范化

<span style="background-color: #8db3e2">**施密特正交化**</span> 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_r$ 线性无关，则可以构造正交向量组 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_r$：

$$\boldsymbol{\beta}_1 = \boldsymbol{\alpha}_1$$

$$\boldsymbol{\beta}_2 = \boldsymbol{\alpha}_2 - \frac{(\boldsymbol{\alpha}_2, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1$$

$$\boldsymbol{\beta}_3 = \boldsymbol{\alpha}_3 - \frac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_1)}{(\boldsymbol{\beta}_1, \boldsymbol{\beta}_1)}\boldsymbol{\beta}_1 - \frac{(\boldsymbol{\alpha}_3, \boldsymbol{\beta}_2)}{(\boldsymbol{\beta}_2, \boldsymbol{\beta}_2)}\boldsymbol{\beta}_2$$

再将 $\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \cdots, \boldsymbol{\beta}_r$ 单位化即可。

---

## 九、正交矩阵

<span style="background-color: #ccc1d9">**定义（正交矩阵）**</span> 若 $n$ 阶矩阵 $\mathbf{A}$ 满足 $\mathbf{A}^T\mathbf{A} = \mathbf{E}$（即 $\mathbf{A}^T = \mathbf{A}^{-1}$），则称 $\mathbf{A}$ 为**正交矩阵**。

<span style="background-color: #8db3e2">**性质**</span>
- $\mathbf{A}$ 为正交矩阵 $\Leftrightarrow$ $\mathbf{A}$ 的行（列）向量组是两两正交的单位向量
- 若 $\mathbf{A}$ 为正交矩阵，则 $|\mathbf{A}| = \pm 1$
- 若 $\mathbf{A}, \mathbf{B}$ 均为正交矩阵，则 $\mathbf{A}\mathbf{B}$ 也是正交矩阵

<span style="background-color: #8db3e2">**定理**</span> 正交变换保持向量的内积和模不变：若 $\mathbf{A}$ 为正交矩阵，则 $(\mathbf{A}\boldsymbol{\alpha}, \mathbf{A}\boldsymbol{\beta}) = (\boldsymbol{\alpha}, \boldsymbol{\beta})$，$\|\mathbf{A}\boldsymbol{\alpha}\| = \|\boldsymbol{\alpha}\|$。

---

## 十、典型例题

### 例题1：线性相关性的判定

**题目**（660题-385）已知向量组 $\alpha_{1} = (1,2,-1,1)^{\mathrm{T}},\alpha_{2} = (2,0,t,0)^{\mathrm{T}},\alpha_{3} = (0,-4,5,t)^{\mathrm{T}}$ 线性无关，则 $t$ 的取值范围为____。

**思路**：利用向量组线性无关的行列式判别法。

**解答**：
构造矩阵 $\mathbf{A} = [\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3]$，计算其行列式：

$|\mathbf{A}| = \begin{vmatrix} 1 & 2 & 0 \\ 2 & 0 & -4 \\ -1 & t & 5 \\ 1 & 0 & t \end{vmatrix}$（按第4行展开有误，应为3列矩阵）

实际上 $\mathbf{A}$ 是 $4 \times 3$ 矩阵，无法直接算行列式。向量组线性无关意味着不存在不全为零的 $k_1, k_2, k_3$ 使 $k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + k_3\boldsymbol{\alpha}_3 = \mathbf{0}$。

设 $k_1\boldsymbol{\alpha}_1 + k_2\boldsymbol{\alpha}_2 + k_3\boldsymbol{\alpha}_3 = \mathbf{0}$，得到方程组：

$$\begin{cases} k_1 + 2k_2 = 0 \\ 2k_1 + tk_3 = 0 \\ -k_1 + 5k_3 = 0 \\ k_1 + tk_3 = 0 \end{cases}$$

由第1式得 $k_1 = -2k_2$。
由第3式得 $k_1 = 5k_3$。
由第2式和第4式得 $2(-2k_2) + tk_3 = 0$ 和 $-2k_2 + tk_3 = 0$，比较得 $tk_3 = 4k_2$。

要使向量组线性无关，方程组只有零解，即 $k_1 = k_2 = k_3 = 0$。

实际上，更直接的方法是计算向量组的秩。化简增广矩阵：

$[\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3] \rightarrow \begin{bmatrix} 1 & 2 & 0 \\ 0 & -4 & -4 \\ 0 & t+2 & 5 \\ 0 & -2 & t \end{bmatrix} \rightarrow \begin{bmatrix} 1 & 2 & 0 \\ 0 & -4 & -4 \\ 0 & t-2 & 1 \\ 0 & 0 & t-2 \end{bmatrix}$

当 $t \neq 2$ 时，向量组的秩为3，线性无关。

**总结**：向量组线性无关的判定通常转化为方程组只有零解或矩阵的秩等于向量的个数。

---

### 例题2：线性表示

**题目**（660题-387）已知 $\alpha_{1} = (1,4,2)^{\mathrm{T}},\alpha_{2} = (2,7,3)^{\mathrm{T}},\alpha_{3} = (0,1,a)^{\mathrm{T}}$ 可以表示任意一个三维向量，则 $a$ 的取值范围为____。

**思路**：向量组能表示任意三维向量意味着该向量组构成 $\mathbb{R}^3$ 的一组基，即向量组线性无关。

**解答**：
要使 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3$ 能表示任意三维向量，它们必须线性无关（构成 $\mathbb{R}^3$ 的一组基）。

构造矩阵 $\mathbf{A} = [\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3]$，计算行列式：

$|\mathbf{A}| = \begin{vmatrix} 1 & 2 & 0 \\ 4 & 7 & 1 \\ 2 & 3 & a \end{vmatrix} = \begin{vmatrix} 1 & 2 & 0 \\ 0 & -1 & 1 \\ 0 & -1 & a \end{vmatrix} = \begin{vmatrix} -1 & 1 \\ -1 & a \end{vmatrix} = -a + 1$

$|\mathbf{A}| \neq 0 \Leftrightarrow 1 - a \neq 0 \Leftrightarrow a \neq 1$

当 $a \neq 1$ 时，$|\mathbf{A}| \neq 0$，向量组线性无关，可以表示任意三维向量。

**总结**：向量组能表示任意向量 $\Leftrightarrow$ 向量组线性无关 $\Leftrightarrow$ 矩阵的行列式 $\neq 0$。

---

### 例题3：向量组的秩

**题目**（660题-388）已知向量组 $\pmb{\alpha}_{1} = (a, a, 1)^{\mathrm{T}}, \pmb{\alpha}_{2} = (a, 1, a)^{\mathrm{T}}, \pmb{\alpha}_{3} = (1, a, a)^{\mathrm{T}}$ 的秩是2，则 $a =$____。

**思路**：向量组的秩为2意味着向量组线性相关，但存在某个2阶子式不为零。

**解答**：
构造矩阵 $\mathbf{A} = [\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3]$，计算其行列式：

$|\mathbf{A}| = \begin{vmatrix} a & a & 1 \\ a & 1 & a \\ 1 & a & a \end{vmatrix} = \begin{vmatrix} a & a & 1 \\ 0 & 1-a & 0 \\ 1-a & 0 & a-1 \end{vmatrix} = (1-a)\begin{vmatrix} a & a & 1 \\ 0 & 1 & 0 \\ 1 & 0 & a-1 \end{vmatrix}$

$= (1-a)[a(a-1) - 1] = (1-a)(a^2 - a - 1) = -(a-1)(a^2 - a - 1)$

当向量组的秩为2时，$|\mathbf{A}| = 0$，即 $(a-1)(a^2 - a - 1) = 0$

解得 $a = 1$ 或 $a = \frac{1 \pm \sqrt{5}}{2}$

但当 $a = 1$ 时，向量组为 $(1,1,1)^T, (1,1,1)^T, (1,1,1)^T$，显然秩为1，不是2。

所以 $a = \frac{1 \pm \sqrt{5}}{2}$

验证：当 $a = \frac{1 + \sqrt{5}}{2}$ 时，$\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3$ 线性相关，但任意两个向量线性无关（如 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 线性无关），所以秩为2。

**总结**：向量组的秩取决于参数值，需要排除使向量组秩更低的情况。

---

### 例题4：过渡矩阵

**题目**（660题-395）已知 $\alpha_{1},\alpha_{2},\alpha_{3}$ 是三维向量空间的一个基底，若

$$\boldsymbol{\beta}_1 = \alpha_1 + \alpha_2 + \alpha_3, \quad \boldsymbol{\beta}_2 = 3\alpha_2 + \alpha_3, \quad \boldsymbol{\beta}_3 = \alpha_1 - \alpha_2$$

则由基 $\alpha_{1}, \alpha_{2}, \alpha_{3}$ 到基 $\beta_{1}, \beta_{2}, \beta_{3}$ 的过渡矩阵是____。

**思路**：利用过渡矩阵的定义 $(\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \boldsymbol{\beta}_3) = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3)\mathbf{C}$。

**解答**：
由题意，

$$(\boldsymbol{\beta}_1, \boldsymbol{\beta}_2, \boldsymbol{\beta}_3) = (\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3) \begin{bmatrix} 1 & 0 & 1 \\ 1 & 3 & -1 \\ 1 & 1 & 0 \end{bmatrix}$$

所以过渡矩阵

$$\mathbf{C} = \begin{bmatrix} 1 & 0 & 1 \\ 1 & 3 & -1 \\ 1 & 1 & 0 \end{bmatrix}$$

**总结**：过渡矩阵的列向量是新基向量在旧基下的坐标。

---

## 十一、解题方法总结

### 11.1 线性相关性判定方法

| 方法 | 适用情况 |
|------|----------|
| 定义法 | 写出 $k_1\boldsymbol{\alpha}_1 + \cdots + k_s\boldsymbol{\alpha}_s = \mathbf{0}$，讨论系数 |
| 行列式法 | 向量个数等于维数时，计算行列式 |
| 秩的方法 | 一般情况，化阶梯形求秩 |

### 11.2 常见易错点

1. **混淆"相关"与"表示"**：$\boldsymbol{\beta}$ 可由 $\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_s$ 表示，不一定相关
2. **维数与向量个数**：$n+1$ 个 $n$ 维向量必相关
3. **极大无关组不唯一**：但秩相同
4. **正交化顺序**：施密特正交化顺序很重要

---

## 十二、练习题精选

### 基础练习

1. 判断下列向量组是否线性相关：
   - $\boldsymbol{\alpha}_1 = (1,2,3)^T, \boldsymbol{\alpha}_2 = (4,5,6)^T, \boldsymbol{\alpha}_3 = (7,8,9)^T$
   - $\boldsymbol{\beta}_1 = (1,0,0)^T, \boldsymbol{\beta}_2 = (0,1,0)^T, \boldsymbol{\beta}_3 = (0,0,1)^T$

2. 设 $\boldsymbol{\alpha}_1 = (1,1,1)^T, \boldsymbol{\alpha}_2 = (1,2,3)^T, \boldsymbol{\alpha}_3 = (1,3,6)^T$，求其极大线性无关组。

3. 将 $\boldsymbol{\alpha}_1 = (1,1,1)^T, \boldsymbol{\alpha}_2 = (1,2,0)^T, \boldsymbol{\alpha}_3 = (3,0,0)^T$ 正交规范化。

### 提高练习

4. 设 $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \cdots, \boldsymbol{\alpha}_n$ 线性无关，证明 $\boldsymbol{\alpha}_1 + \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_2 + \boldsymbol{\alpha}_3, \cdots, \boldsymbol{\alpha}_n + \boldsymbol{\alpha}_1$ 线性相关的充要条件是 $n$ 为偶数。

5. 设 $\mathbf{A}$ 为 $n$ 阶正交矩阵，证明 $|\mathbf{A}| = \pm 1$。

---

## 参考答案提示

1. (1) 线性相关（三个向量和为常数向量，和为0）；(2) 线性无关（单位坐标向量组）

2. $\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2$ 是一个极大线性无关组

3. 先正交化，再单位化
   - $\boldsymbol{\beta}_1 = (1,1,1)^T$
   - $\boldsymbol{\beta}_2 = (1,2,0)^T - \frac{3}{3}(1,1,1)^T = (0,1,-1)^T$
   - $\boldsymbol{\beta}_3 = (3,0,0)^T - \frac{3}{3}(1,1,1)^T - \frac{-1}{2}(0,1,-1)^T = (2,-1,0.5)^T$
   - 单位化即得正交规范基

4. 提示：构造方程 $k_1(\boldsymbol{\alpha}_1 + \boldsymbol{\alpha}_2) + \cdots + k_n(\boldsymbol{\alpha}_n + \boldsymbol{\alpha}_1) = \mathbf{0}$，利用 $\boldsymbol{\alpha}_1, \cdots, \boldsymbol{\alpha}_n$ 线性无关得方程组，分析系数矩阵的行列式

5. 由 $\mathbf{A}^T\mathbf{A} = \mathbf{E}$ 得 $|\mathbf{A}|^2 = 1$，故 $|\mathbf{A}| = \pm 1$

---

> **注**：本 Lecture 内容涵盖向量和向量组的核心知识点。建议结合《基础过关660题》第377-396题进行练习巩固。
