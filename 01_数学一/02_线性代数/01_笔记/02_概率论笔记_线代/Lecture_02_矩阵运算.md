---
title: Lecture 02 - 矩阵运算
subject: 线性代数
chapter: 第二章
lecture: 02
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 02: 矩阵运算

## 一、矩阵的概念与基本运算

### 1.1 矩阵的定义

<span style="background-color: #ccc1d9">**定义（矩阵）**</span> 由 $m \times n$ 个数 $a_{ij}$ 排成的 $m$ 行 $n$ 列的数表

$$\begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$$

称为 $m \times n$ 矩阵，记作 $\mathbf{A} = (a_{ij})_{m \times n}$。

### 1.2 矩阵的基本运算

**加法**：两个同型矩阵对应元素相加

<span style="background-color: #8db3e2">**性质**</span> 设 $\mathbf{A}, \mathbf{B}, \mathbf{C}$ 为同型矩阵，则：
- $\mathbf{A} + \mathbf{B} = \mathbf{B} + \mathbf{A}$（交换律）
- $(\mathbf{A} + \mathbf{B}) + \mathbf{C} = \mathbf{A} + (\mathbf{B} + \mathbf{C})$（结合律）

**数乘**：数 $k$ 与矩阵 $\mathbf{A}$ 的乘积，记作 $k\mathbf{A}$，等于 $k$ 乘以 $\mathbf{A}$ 的每个元素。

<span style="background-color: #8db3e2">**性质**</span>
- $(kl)\mathbf{A} = k(l\mathbf{A})$
- $k(\mathbf{A} + \mathbf{B}) = k\mathbf{A} + k\mathbf{B}$
- $(k + l)\mathbf{A} = k\mathbf{A} + l\mathbf{A}$

**转置**：将矩阵 $\mathbf{A}$ 的行列互换，记作 $\mathbf{A}^T$ 或 $\mathbf{A}'$。

<span style="background-color: #8db3e2">**性质**</span>
- $(\mathbf{A}^T)^T = \mathbf{A}$
- $(\mathbf{A} + \mathbf{B})^T = \mathbf{A}^T + \mathbf{B}^T$
- $(k\mathbf{A})^T = k\mathbf{A}^T$
- $(\mathbf{A}\mathbf{B})^T = \mathbf{B}^T\mathbf{A}^T$

---

## 二、矩阵的乘法及运算律

### 2.1 矩阵乘法

<span style="background-color: #ccc1d9">**定义（矩阵乘法）**</span> 设 $\mathbf{A} = (a_{ij})_{m \times s}$，$\mathbf{B} = (b_{ij})_{s \times n}$，则 $\mathbf{C} = \mathbf{A}\mathbf{B} = (c_{ij})_{m \times n}$，其中

$$c_{ij} = \sum_{k=1}^{s} a_{ik}b_{kj}$$

### 2.2 乘法运算律

<span style="background-color: #8db3e2">**性质**</span>
- $(\mathbf{A}\mathbf{B})\mathbf{C} = \mathbf{A}(\mathbf{B}\mathbf{C})$（结合律）
- $\mathbf{A}(\mathbf{B} + \mathbf{C}) = \mathbf{A}\mathbf{B} + \mathbf{A}\mathbf{C}$（左分配律）
- $(\mathbf{A} + \mathbf{B})\mathbf{C} = \mathbf{A}\mathbf{C} + \mathbf{B}\mathbf{C}$（右分配律）
- $k(\mathbf{A}\mathbf{B}) = (k\mathbf{A})\mathbf{B} = \mathbf{A}(k\mathbf{B})$

<span style="background-color: #8db3e2">**注意**</span> 矩阵乘法**不满足**交换律，即一般情况下 $\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$。

---

## 三、方阵的幂

<span style="background-color: #ccc1d9">**定义（方阵的幂）**</span> 设 $\mathbf{A}$ 为 $n$ 阶方阵，定义

$$\mathbf{A}^k = \underbrace{\mathbf{A} \cdot \mathbf{A} \cdot \cdots \cdot \mathbf{A}}_{k \text{ 个}}$$

<span style="background-color: #8db3e2">**性质**</span>
- $\mathbf{A}^m \mathbf{A}^n = \mathbf{A}^{m+n}$
- $(\mathbf{A}^m)^n = \mathbf{A}^{mn}$

<span style="background-color: #8db3e2">**重要公式**</span>
- $(k\mathbf{A})^n = k^n \mathbf{A}^n$
- $(\mathbf{A}\mathbf{B})^n \neq \mathbf{A}^n \mathbf{B}^n$（一般情况下）

---

## 四、矩阵的逆

### 4.1 逆矩阵的定义

<span style="background-color: #ccc1d9">**定义（逆矩阵）**</span> 设 $\mathbf{A}$ 为 $n$ 阶方阵，若存在 $n$ 阶矩阵 $\mathbf{B}$ 使得

$$\mathbf{A}\mathbf{B} = \mathbf{B}\mathbf{A} = \mathbf{E}$$

则称 $\mathbf{A}$ 为**可逆矩阵**，称 $\mathbf{B}$ 为 $\mathbf{A}$ 的逆矩阵，记作 $\mathbf{B} = \mathbf{A}^{-1}$。

### 4.2 逆矩阵的性质

<span style="background-color: #8db3e2">**性质**</span>
- 若 $\mathbf{A}$ 可逆，则 $\mathbf{A}^{-1}$ 唯一
- $(\mathbf{A}^{-1})^{-1} = \mathbf{A}$
- $(k\mathbf{A})^{-1} = \frac{1}{k}\mathbf{A}^{-1}$（$k \neq 0$）
- $(\mathbf{A}\mathbf{B})^{-1} = \mathbf{B}^{-1}\mathbf{A}^{-1}$
- $(\mathbf{A}^T)^{-1} = (\mathbf{A}^{-1})^T$

### 4.3 矩阵可逆的判定

<span style="background-color: #8db3e2">**定理**</span> $n$ 阶矩阵 $\mathbf{A}$ 可逆的充要条件：
1. $|\mathbf{A}| \neq 0$
2. $r(\mathbf{A}) = n$（满秩）
3. $\mathbf{A}$ 的行（列）向量组线性无关
4. $\mathbf{A}$ 可以表示为初等矩阵的乘积

---

## 五、伴随矩阵

### 5.1 伴随矩阵的定义

<span style="background-color: #ccc1d9">**定义（伴随矩阵）**</span> 由矩阵 $\mathbf{A}$ 的代数余子式构成的矩阵的转置，记作 $\mathbf{A}^*$：

$$\mathbf{A}^* = \begin{bmatrix} A_{11} & A_{21} & \cdots & A_{n1} \\ A_{12} & A_{22} & \cdots & A_{n2} \\ \vdots & \vdots & & \vdots \\ A_{1n} & A_{2n} & \cdots & A_{nn} \end{bmatrix}$$

其中 $A_{ij}$ 是元素 $a_{ij}$ 的代数余子式。

### 5.2 伴随矩阵的性质

<span style="background-color: #8db3e2">**定理**</span> 对于 $n$ 阶矩阵 $\mathbf{A}$，有

$$\mathbf{A}\mathbf{A}^* = \mathbf{A}^*\mathbf{A} = |\mathbf{A}|\mathbf{E}$$

<span style="background-color: #8db3e2">**重要推论**</span> 若 $|\mathbf{A}| \neq 0$，则

$$\mathbf{A}^{-1} = \frac{1}{|\mathbf{A}|}\mathbf{A}^*$$

---

## 六、矩阵的初等变换

### 6.1 初等变换的类型

<span style="background-color: #ccc1d9">**定义（初等行变换）**</span>
1. **交换**：互换两行（记作 $r_i \leftrightarrow r_j$）
2. **倍乘**：某行乘以非零常数 $k$（记作 $k r_i$）
3. **倍加**：某行的 $k$ 倍加到另一行（记作 $r_i + k r_j$）

### 6.2 初等矩阵

<span style="background-color: #ccc1d9">**定义（初等矩阵）**</span> 由单位矩阵经过一次初等变换得到的矩阵。

<span style="background-color: #8db3e2">**性质**</span> 左乘初等矩阵等于对矩阵作相应的行变换；右乘初等矩阵等于对矩阵作相应的列变换。

---

## 七、矩阵的秩

### 7.1 矩阵秩的定义

<span style="background-color: #ccc1d9">**定义（矩阵的秩）**</span> 矩阵 $\mathbf{A}$ 中非零子式的最高阶数，记作 $r(\mathbf{A})$ 或 $R(\mathbf{A})$。

### 7.2 秩的性质

<span style="background-color: #8db3e2">**性质**</span>
- $0 \leq r(\mathbf{A}) \leq \min\{m, n\}$
- $r(\mathbf{A}^T) = r(\mathbf{A})$
- $r(\mathbf{A}\mathbf{B}) \leq \min\{r(\mathbf{A}), r(\mathbf{B})\}$
- $r(\mathbf{A} + \mathbf{B}) \leq r(\mathbf{A}) + r(\mathbf{B})$
- 若 $\mathbf{A}$ 可逆，则 $r(\mathbf{A}\mathbf{B}) = r(\mathbf{B})$

<span style="background-color: #8db3e2">**定理**</span> 初等变换不改变矩阵的秩。

---

## 八、分块矩阵

### 8.1 分块矩阵的概念

<span style="background-color: #ccc1d9">**定义（分块矩阵）**</span> 将矩阵用横线和纵线分成若干块，每一块称为矩阵的一个子块。

### 8.2 分块矩阵的运算

<span style="background-color: #8db3e2">**加法**</span> 同结构的分块矩阵可以相加。

<span style="background-color: #8db3e2">**数乘**</span> 数乘每个子块。

<span style="background-color: #8db3e2">**乘法**</span> 分块相乘时，左边矩阵的列分块方式必须与右边矩阵的行分块方式一致。

### 8.3 常见分块运算

<span style="background-color: #8db3e2">**分块对角矩阵**</span> 若 $\mathbf{A} = \begin{bmatrix} \mathbf{A}_1 & 0 \\ 0 & \mathbf{A}_2 \end{bmatrix}$，则：
- $|\mathbf{A}| = |\mathbf{A}_1||\mathbf{A}_2|$
- $\mathbf{A}^{-1} = \begin{bmatrix} \mathbf{A}_1^{-1} & 0 \\ 0 & \mathbf{A}_2^{-1} \end{bmatrix}$

---

## 九、典型例题

### 例题1：矩阵的幂

**题目**（660题-369）设 $\boldsymbol{\alpha}=(1,3,-2)^{\mathrm{T}},\boldsymbol{\beta}=(2,0,0)^{\mathrm{T}},\boldsymbol{A}=\boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}}$，则 $A^3=$ ____。

**思路**：利用矩阵乘法的结合律，将 $\mathbf{A}$ 写成列向量乘行向量的形式。

**解答**：
$\mathbf{A} = \boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}} = \begin{bmatrix} 1 \\ 3 \\ -2 \end{bmatrix}[2,0,0] = \begin{bmatrix} 2 & 0 & 0 \\ 6 & 0 & 0 \\ -4 & 0 & 0 \end{bmatrix}$

$\mathbf{A}^2 = \mathbf{A} \cdot \mathbf{A} = (\boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}})(\boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}}) = \boldsymbol{\alpha}(\boldsymbol{\beta}^{\mathrm{T}}\boldsymbol{\alpha})\boldsymbol{\beta}^{\mathrm{T}}$

计算 $\boldsymbol{\beta}^{\mathrm{T}}\boldsymbol{\alpha} = [2,0,0]\begin{bmatrix} 1 \\ 3 \\ -2 \end{bmatrix} = 2$

所以 $\mathbf{A}^2 = 2\boldsymbol{\alpha}\boldsymbol{\beta}^{\mathrm{T}} = 2\mathbf{A}$

$\mathbf{A}^3 = \mathbf{A}^2 \cdot \mathbf{A} = 2\mathbf{A} \cdot \mathbf{A} = 2\mathbf{A}^2 = 4\mathbf{A} = \begin{bmatrix} 8 & 0 & 0 \\ 24 & 0 & 0 \\ -16 & 0 & 0 \end{bmatrix}$

**总结**：当矩阵可表示为列向量乘行向量时，利用结合律可简化计算。

---

### 例题2：逆矩阵的求解

**题目**（660题-373）若 $\mathbf{A} = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 1 \end{bmatrix}$，则 $(\frac{1}{3}\mathbf{A})^{-1} =$ ____。

**思路**：利用分块矩阵的求逆公式和矩阵乘法的结合律。

**解答**：
设 $\mathbf{A} = \mathbf{A}_1 \mathbf{A}_2 \mathbf{A}_3$

$\mathbf{A}_1 = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix}$，$\mathbf{A}_2 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{bmatrix}$，$\mathbf{A}_3 = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 1 \end{bmatrix}$

先求各个矩阵的逆：

$\mathbf{A}_1^{-1} = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix}$（$\mathbf{A}_1$ 是初等矩阵）

$\mathbf{A}_2^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & -2 \\ 0 & 0 & 1 \end{bmatrix}$（下三角矩阵）

$\mathbf{A}_3^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \frac{1}{3} & 0 \\ 0 & 0 & 1 \end{bmatrix}$

$(\frac{1}{3}\mathbf{A})^{-1} = 3\mathbf{A}^{-1} = 3\mathbf{A}_3^{-1}\mathbf{A}_2^{-1}\mathbf{A}_1^{-1}$

计算 $\mathbf{A}_2^{-1}\mathbf{A}_1^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & -2 \\ 0 & 0 & 1 \end{bmatrix}\begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix} = \begin{bmatrix} 0 & 0 & 1 \\ -2 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix}$

再乘以 $\mathbf{A}_3^{-1}$：

$(\frac{1}{3}\mathbf{A})^{-1} = 3\begin{bmatrix} 1 & 0 & 0 \\ 0 & \frac{1}{3} & 0 \\ 0 & 0 & 1 \end{bmatrix}\begin{bmatrix} 0 & 0 & 1 \\ -2 & 1 & 0 \\ 1 & 0 & 0 \end{bmatrix} = 3\begin{bmatrix} 0 & 0 & 1 \\ -\frac{2}{3} & \frac{1}{3} & 0 \\ 1 & 0 & 0 \end{bmatrix} = \begin{bmatrix} 0 & 0 & 3 \\ -2 & 1 & 0 \\ 3 & 0 & 0 \end{bmatrix}$

**总结**：利用矩阵乘法的结合律和初等矩阵的逆的性质简化计算。

---

### 例题3：矩阵方程

**题目**（660题-374）已知矩阵 $\mathbf{A} = \begin{bmatrix} 3 & 0 & 0 \\ 0 & 1 & -1 \\ 0 & 2 & 3 \end{bmatrix}, \mathbf{B} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 1 & 0 & 1 \end{bmatrix}$，若矩阵 $\mathbf{X}$ 满足 $A\mathbf{X} = \mathbf{B} + 2\mathbf{X}$，则 $\mathbf{X} =$。

**思路**：将方程变形为 $(\mathbf{A} - 2\mathbf{E})\mathbf{X} = \mathbf{B}$，然后求逆。

**解答**：
由 $A\mathbf{X} = \mathbf{B} + 2\mathbf{X}$ 得 $(\mathbf{A} - 2\mathbf{E})\mathbf{X} = \mathbf{B}$

$\mathbf{A} - 2\mathbf{E} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & -1 \\ 0 & 2 & 1 \end{bmatrix}$

求 $(\mathbf{A} - 2\mathbf{E})^{-1}$：

$|\mathbf{A} - 2\mathbf{E}| = \begin{vmatrix} 1 & 0 & 0 \\ 0 & -1 & -1 \\ 0 & 2 & 1 \end{vmatrix} = 1 \times (-1 - (-2)) = 1$

伴随矩阵 $(\mathbf{A} - 2\mathbf{E})^* = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & 1 \\ 0 & 0 & -1 \end{bmatrix}$

所以 $(\mathbf{A} - 2\mathbf{E})^{-1} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & 1 \\ 0 & 0 & -1 \end{bmatrix}$

$\mathbf{X} = (\mathbf{A} - 2\mathbf{E})^{-1}\mathbf{B} = \begin{bmatrix} 1 & 0 & 0 \\ 0 & -1 & 1 \\ 0 & 0 & -1 \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 1 & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 \\ 1 & -1 & 1 \\ -1 & 0 & -1 \end{bmatrix}$

**总结**：矩阵方程求解的基本方法是移项、提因子、求逆。

---

### 例题4：矩阵的秩

**题目**（660题-375）已知 $\mathbf{A} = \begin{bmatrix} 1 & 1 & a & 4 \\ 1 & 0 & 2 & a \\ -1 & a & 1 & 0 \end{bmatrix}, r(\mathbf{A}) = 3$，则 $a$ 的取值范围为 ____。

**思路**：利用矩阵秩的定义和行列式计算。

**解答**：
$r(\mathbf{A}) = 3$ 意味着所有4阶子式均为零（不存在4阶非零子式）。

考虑3阶子式（取1、2、3列和1、2、4列等）：

$\begin{vmatrix} 1 & 1 & a \\ 1 & 0 & 2 \\ -1 & a & 1 \end{vmatrix} = \begin{vmatrix} 1 & 1 & a \\ 0 & -1 & 2-a \\ 0 & a+1 & 1+a \end{vmatrix} = -(1+a)(1+a) + (2-a)(a+1) = -(1+a)^2 + (2-a)(a+1) = 0$

展开：$-(1 + 2a + a^2) + (2 + a - a^2 - 2a) = -1 - 2a - a^2 + 2 - a - a^2 = 1 - 3a - 2a^2 = 0$

即 $2a^2 + 3a - 1 = 0$，解得 $a = \frac{-3 \pm \sqrt{9 + 8}}{4} = \frac{-3 \pm \sqrt{17}}{4}$

还需验证：当 $a = \frac{-3 + \sqrt{17}}{4}$ 或 $a = \frac{-3 - \sqrt{17}}{4}$ 时，$r(\mathbf{A}) = 3$。

实际上，更直接的方法是计算行列式因子：

由 $r(\mathbf{A}) = 3$ 可知 $|\mathbf{A}| = 0$（如果有3阶非零子式则需要验证）。

经过计算，当 $a \neq 1$ 时，$r(\mathbf{A}) = 3$。但更精确地说：

从 $\begin{vmatrix} 1 & 1 & 4 \\ 1 & 0 & a \\ -1 & 1 & 0 \end{vmatrix} = 0$ 可解出 $a$ 的取值。

最终答案是 $a \neq -1$ 且满足上述方程。

**总结**：矩阵秩的问题通常转化为行列式计算。

---

## 十、解题方法总结

### 10.1 矩阵运算常见方法

| 类型 | 方法 |
|------|------|
| 矩阵幂运算 | 寻找规律、利用结合律、分块对角化 |
| 求逆矩阵 | 伴随矩阵法、初等变换法 |
| 矩阵方程 | 移项、提因子、求逆 |
| 秩的问题 | 化阶梯形、行列式计算 |

### 10.2 常见易错点

1. **矩阵乘法不可交换**：$\mathbf{A}\mathbf{B} \neq \mathbf{B}\mathbf{A}$
2. **逆矩阵公式**：$(\mathbf{A}\mathbf{B})^{-1} = \mathbf{B}^{-1}\mathbf{A}^{-1}$，顺序颠倒
3. **转置与逆**：$(\mathbf{A}\mathbf{B})^T = \mathbf{B}^T\mathbf{A}^T$，$(\mathbf{A}\mathbf{B})^{-1} = \mathbf{B}^{-1}\mathbf{A}^{-1}$
4. **数乘与幂**：$(k\mathbf{A})^n = k^n\mathbf{A}^n$，但 $(\mathbf{A}^n)^m = \mathbf{A}^{nm}$

---

## 十一、练习题精选

### 基础练习

1. 设 $\mathbf{A} = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$，求 $\mathbf{A}^{-1}$。

2. 设 $\mathbf{A} = \begin{bmatrix} 2 & 1 & 0 \\ 1 & 0 & 1 \\ 0 & 1 & 2 \end{bmatrix}$，求 $|\mathbf{A}|$。

3. 若 $\mathbf{A}^2 = \mathbf{A}$（幂等矩阵），证明 $\mathbf{A}$ 可逆时 $\mathbf{A} = \mathbf{E}$。

### 提高练习

4. 设 $\mathbf{A} = \begin{bmatrix} 1 & 0 & 1 \\ 0 & 2 & 0 \\ 1 & 0 & 1 \end{bmatrix}$，求 $\mathbf{A}^n$。

5. 设 $\mathbf{A}, \mathbf{B}$ 均为 $n$ 阶矩阵，且 $\mathbf{A} + \mathbf{B} = \mathbf{E}$，证明 $r(\mathbf{A}) + r(\mathbf{B}) \geq n$。

---

## 参考答案提示

1. $\mathbf{A}^{-1} = \frac{1}{-2}\begin{bmatrix} 4 & -2 \\ -3 & 1 \end{bmatrix} = \begin{bmatrix} -2 & 1 \\ \frac{3}{2} & -\frac{1}{2} \end{bmatrix}$

2. $|\mathbf{A}| = 2$

3. 提示：由 $\mathbf{A}^2 = \mathbf{A}$ 得 $\mathbf{A}(\mathbf{A} - \mathbf{E}) = \mathbf{O}$，两边取行列式得 $|\mathbf{A}||\mathbf{A} - \mathbf{E}| = 0$，由 $|\mathbf{A}| \neq 0$ 得 $\mathbf{A} = \mathbf{E}$

4. 利用特征值分解或数学归纳法

5. 提示：由 $\mathbf{A} + \mathbf{B} = \mathbf{E}$ 得 $r(\mathbf{A} + \mathbf{B}) = n$，又 $r(\mathbf{A} + \mathbf{B}) \leq r(\mathbf{A}) + r(\mathbf{B})$

---

> **注**：本 Lecture 内容涵盖矩阵运算的核心知识点。建议结合《基础过关660题》第368-376题进行练习巩固。
